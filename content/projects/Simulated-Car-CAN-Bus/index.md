---
layout: page
permalink: "simulated-car-CAN-bus"
title: "Simulated Car CAN Bus"
date: 2023-09-05
showAuthor: true
showDate: true
showReadingTime: false
showTableOfContents: true
showSummary: True
# layout: simple
summary: "A simple CAN bus demonstration"
---

# Overview

This is a CAN bus project I made for a short, 2 week final project. The project goal was to simulate a car can bus with two MCU's. One MCU read sensor input and sent it over the CAN bus. The other read data from the CAN bus and displayed the status of the sensors. I wrote a SPI driver for the texas instruments board, because it lacked a CAN peripheral onboard, a library using my SPI driver for a SPI to CAN controller, a CAN driver for a STM32 board, and application code for each MCU (including configuring all the peripheral registers, interrupts, ADCs, and timers). In this image I am verifying my library for the SPI to CAN controller. Specifically, I am looking at SPI frames coming from my library and comparing them against the controllers datasheet. I have an arduino connected with the same controller on the CAN bus running a known, good and tested library to verify if my library was sending and receiving CAN messages correctly.
{{< figure src="images/simulated-car-CAN-bus.jpeg">}}
