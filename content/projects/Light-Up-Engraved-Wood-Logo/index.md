---
layout: page
permalink: "rose-leaf"
title: "Light Up Engraved Wooden Logo"
date: 2023-12-12
showAuthor: true
showDate: true
showReadingTime: false
showTableOfContents: true
showSummary: True
# layout: simple
summary: "Blending wood working and electronics" 
---

# Overview
I wanted to make a christmas gift for some family members and I came up with this. My roommate had designed this maple leaf with our school logo in the center for the school to 3D print and give out. I thought it would be really cool to waterjet the leaf out of metal and paint it. And then the idea snowballed from there... What I ended up with was a combination of an electrical and woodworking project. Part of what made this a cool project was how many tools I got to use making it: waterjet, table router, hand router, sand blaster, soldering tools, lab bench supplies, etc.
{{< figure src="images/rose-leaf-1.jpeg">}}  


I did change from a 2K resistor for the LEDS. My batteries ended up giving me around a 6V supply. The LEDS are not at full brightness because there are 8 of them. But, that's ok for this project. Dimmer is actually better for what I wanted.


{{< figure src="images/rose-leaf-2.jpeg">}}
I used a simple RC circuit to hold the base of a mosfet on to keep the LEDS on. There is a small button routed into the side of the wood, where the black paint is on the left of this image. Knowing the time constant, tau, is RC, and that in 4 tau a circuit will charge to, or discharge to, ~98% of its final value, I found a RC pair that got me a few seconds of on time as a starting value. I played with the values on a breadboard from there to see what values I liked. Because the charge and discharge is exponential the lights ended up with a nice fade effect too. 

The hardest part of this mini project ended up being the batteries! Making a battery holder was surprisingly difficult! Not it theory, but in practice... I also tried to make a diffuser for the LEDS by putting a layer of epoxy in front of them. This worked ok but not great.
