---
title: PRR Position Lights
---
# SimpleSig and Pennsylvania Position Lights

## Overview

The first railroad block signals that came into widespread use in the US (and elsewhere) were largely semaphores.  In an era where electric light bulbs relatively short-lived and dim, and commercial electric power was not widespread, the semaphore had a good number of advantages.  During daylight, the crew could see the blade and had no need to see any sort of light.  At night, a single dim light source was enough to shine through the roundel and communicate the same thing in darkness.  They could also be purely mechanical, driven by rods and levers from the interlocking plant or station and the light provided by an oil lamp.  

They also had a lot of problems.  They were fundamentally mechanical devices, even when driven by electric motors rather than rods and levers, and as such were finicky and required significant maintenance.  They were hard to see in inclimate weather.  If the single bulb failed, they were difficult to read a night with the dim headlights of the era.  They also were prone to confusing indications if the sun struck the roundels in certain ways, shining through much brighter than the light source.

They were the best available technology for the era, and after 1898, the electric semaphore became the go-to signal technology.  

However, with light bulb brightness and lifespan climbing, railroads began to search for better options.  The Pennsylvania - ever the innovator - began experimenting with rows of lights that emulated semaphore arms around 1915.  These were known as early "position lights," where a row of lit indications in a vertical, horizontal, or diagonal indication would emulate a semaphore arm.  It had the advantage of being easy to see in any weather and, if a single bulb was out, the crew could still read the indication properly.  They even chose a specific shade of amber for all of their lenses to specifically pick a color that would cut through heavy fog common across their territory.

Around 1921, the PRR standardized on the rows of three bulbs on a round signal head that most people are familiar with as a PRR Position Light today.  PRR signals were largely speed-based, and could be one or two heads on a mast.  They also came up with several forms of dwarf position light, again emulating semaphore arms but here only using two lights to do it.

## The Prototype

Starting around 1955, the PRR started substituting red lenses for the two horizontal lights for the stop indication, and rewiring signals to extinguish the center lamp when stop was being displayed.  This became known as the "snake eyes" or "red eyes" change, and spread across the system in the 1960s.  The rest of the lamps remained the distinctive PRR yellow.

On the former Pennsylvania part of the Northeast Corridor (NEC), essentially from New York down to Washington, DC, Amtrak has converted the old position lights to something that railfans have come to call "Position Color Lights".  These remove the center lamp on most heads, and replace the all-yellow Pennsy lights with standard colored lenses.   The two vertical lights get green lenses, the lower left-upper right diagonal gets standard AREMA yellow lenses, and the horizontal two lights get red lenses.  In places where a restricting aspect is used, the upper left-lower right diagonal gets lunars.  The aspects mostly remain the same, though some - such as flashing green - have been added for newer uses cases.

##  Modeling and SimpleSig

For the most part, PRR position lights are pretty easy to connect to the SimpleSig boards.  The standard red/yellow/green map well to the various PRR aspects and produce indications that - even if not perfectly prototypical - at least make sense.  

The one catch is lighting the center LED.  It needs to have its own wire coming out of the signal head, separate from any of the outer lights.

To connect it, you'll need to add a resistor and 2-3 diodes.  

Take the wire for the center lamp and connect it to a resistor.  Connect the output of that resistor to diodes going into each of the color outputs where you want the center to be on.  If you're modeling earlier PRR signals where the center lamp is always lit as part of an aspect, you need three - one diode into each output line.  If you're modeling a modernized "snake eyes" version where the stop aspect is only the two outer horizontal lamps (and they're now red), then you need 2 diodes, running into yellow and green only.

The diodes can be pretty much any common small silicon diode - 1N400x (4001, 4002, whatever) or 1N914 will work just fine.  I would start with the resistor value at 390 ohms and play with it from there.  Different LEDs will have different drops.  Increasing the resistor value will dim the light, and decreasing it will.

If your signals are common cathode (negative) rather than common anode (positive) as shown in the diagram, turn the diodes around.

For point-end signals of sidings, just leave the lower red output disconnected from the Switch Signal Basic.
