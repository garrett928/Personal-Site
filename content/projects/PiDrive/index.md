---
layout: page
permalink: "pidrive"
title: "PiDrive - Car Data Logger"
date: 2024-10-26
showAuthor: true
showDate: true
showReadingTime: false
showTableOfContents: true
showSummary: True
draft: false
# layout: simple
summary: "Car data logging stack with raspberry pi collection front end and Java Spring Boot API backend "
---

# Pi-Drive

Car data logging stack with raspberry pi collection front end and Java Spring Boot API backend. Every vehical sold in the US since 1996 is required to support the OBD-II protocol. OBD-II is focused on providing emissions data and exposes things like fuel consumption, coolant temperature, vehical speed, engine RPM, etc. This data can be useful for gaining an insight into your cars performance, especially if you have an older car like mine with the check engine light stuck on. The goal of this project is to record as much OBD data as I can and then visualize it in Grafana. I'm not a car guy and I'm not interested in tuning or getting max performance out of my car. I simply want to monitor its health and properly maintain it. Cars are expensive!

## Techologies Used

- Java Spring Boot
- RESTFul API
- [InfluxDB](https://www.influxdata.com/) (Timeseries SQL database)
- Docker
- [Grafana](https://grafana.com/grafana/) (Visualization)
- Anisble (Automate raspberry pi configuration)
- Python
- [OBD-II](https://www.csselectronics.com/pages/obd2-explained-simple-intro)

# Overview
The data collection is handeled by a bluetooth OBD reader and a raspberry pi. When powered on the pi continously checks for the bluetooth dongle and, if present, reads data from it. The data is then written to a local database on the pi. Also while powered on, another process is continously checking if I'm connected to my home wifi. If I am connected to my wifi then this process will ask my telemetry server what was the timestamp of the last piece of data it received. If the timestamp for the latest data on the local raspberry pi database is more recent than the timestamp of the telemetry server then the raspberry pi will send telemetry records one at a time to the telemetry server. This is nice because if the pi looses connection to the telemetry server (e.g I drive my car somewhere else) then the pi will pick up where it left off the next time its within range of my wifi. 

{{< figure src="images/PiDrive-pi-diagram.png">}}  

The telemetry server is a simple RESTful API written in Java using the Spring Boot framework. It only has two core jobs: receive telemetry data and write telemetry data to InfluxDB. Before telemetry data can be received the server must be told about the existance of a car via the `/cars` endpoint. After the server is told about a car a unique ID is generated and telemetry data can be sent to the server via the `/cars/{id}/telemetry` endpoint. To check what cars exist and find a car's id the `/cars` endpoint can be queried.  

{{< figure src="images/PiDrive-api-server.png">}}  



# Recreate the project
Checkout my [github](https://github.com/garrett928/Pi-Drive) for steps on recreating this project.


# Useful Resources

- [HTTP 1.1 standard](https://www.ietf.org/rfc/rfc2616.txt) lays out the definition and uses of GET, POST, PUT, and delete
- [REST APIS vs RPC](https://roy.gbiv.com/untangled/2008/rest-apis-must-be-hypertext-driven) What actually makes something RESTful? Using HTTP request is not enough
- [Hypertext Application Language (HAL)](https://stateless.co/hal_specification.html) how to navigate hyperlink resources in an API
- [Getting started with spring RESTful API](https://spring.io/guides/tutorials/rest) a pretty indepth guide at setting up spring to serve a RESTful API
- [InfluxDB data point](https://docs.influxdata.com/influxdb/v2/reference/key-concepts/data-elements/#Copyright) how data is stored in InfluxDB
  - [How you should design a schema](https://docs.influxdata.com/influxdb/v2/write-data/best-practices/schema-design/)
  - [High Series Cardinality](https://docs.influxdata.com/influxdb/v2/write-data/best-practices/resolve-high-cardinality/) How and why to avoid high series cardinality
