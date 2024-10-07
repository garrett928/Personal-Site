---
layout: page
permalink: "Switching-Power-Supplies"
title: "Switching Power Supples"
date: 2023-09-10
showAuthor: true
showDate: true
showReadingTime: false
showTableOfContents: True
showSummary: True
summary: "A boost and buckboost power supply"
---

# Overview
During college I took an elective on switching power supplies. During the 10 week period, my lab partner and I designed and built a linear power supply (120V AC -> 15V DC), a boost converter (12-14V -> 25V), and a buck boost converter (12-14V -> -25V). This was a very hands on course which tought me many practical skills. My biggest take away from this course was the impact of layout on the performance of a circuit, or even if the circuit works at all.

# Boost Converter
{{< figure src="images/boost-converter-top.jpeg">}}
A boost converter I built in 2023 for a power supply course. The converter is built for 12-14V in and 25V out at 2A. During this course I also built a 120V AC-DC linear power supply, also rated for 25V at 2A.  

{{< figure src="images/boost-converter-bottom.jpeg">}}
Shown here is the bottom of the boost converter. We used wire wrapping instead of soldering for any non-high current connections. This largely due to preference of the instructor, but it was a nice skill to learn and definitely had some advantages during debugging with easily being able to unwrap a pin on an IC.  

{{< figure src="images/boost-converter-schematic.jpeg">}}
Here is my annotated schematic for the boost converter. For this course we were taught the theory and operation of various power supply typologies and then had to go actually design and build them. Although we were provided the schematic for the labs, this was to speed up the lab process to complete building three power supplies in 10 weeks. Most parts were calculated and then picked by the students, as seen by the empty part values on the schematic. I used mathcad and some equations for a boost converter, along with IC datasheets, to pick components to guarantee output ripple, output voltage and switching time.  

# Buck Converter

{{< figure src="images/buck-boost-converter.jpeg">}}
The third power supply I built was a buck-boost converter for 12-14V in and -25V out at 2A.  

{{< figure src="images/buck-boost-converter-bottom.jpeg">}}
Shown here is the bottom of the buck-boost supply. Something that I learned from this project was the careful consideration for the physical construction of a switching power supply. Specifically, the need to minimize the area of the two high current loops on the input and output because of their ability to create lots of EMI. This was actually an issue for my power supply that was hard to debug. The issue was that there was so much noise being generated that the current sense wire on the SG2535A would pick up the noise and trigger the current limit, a pulse-by-pulse current limit, turning off the gate driver for that pulse and turning off the power supply output.  

{{< figure src="images/buck-boost-schematic.png">}}
Here is the schematic for the buck-bojpegost converter. Unfortunately, I've lost my annotated notes for this power supply. This power supply I actually struggled to get  the last piece working (the -12V inverting charge pump shown in the middle right). The charge pump is driven by a 555 timer and is used to supply the negative rail to the LM324 op amp.
