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
draft: True
# layout: simple
summary: "Software stack to collect and monitor car telemetry following a micro-service architecture model"
---

# Overview
During my freshman year I wanted a way to turn on and off a set of lights in my room without getting out of bed. Although slightly overkill, I decided to make a latching circuit. This is the prototype of the circuit.  
{{< figure src="images/room-light-control.jpeg">}}

Here is my latching circuit on perf board and mounted to my loft. It's nothing fancy but served its purpose and I used it many times a day for the entire year. It never failed me! The latch would toggle a relay, which turned on and off a set of rope lights. Something scrappy I did was take a usb charging brick and steal the 5V pins from its output USB to get 5V to my circuit from AC wall power.
{{< figure src="images/room-light-control-2.jpeg">}}

