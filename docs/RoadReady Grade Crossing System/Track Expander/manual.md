---
title: User Manual
---
# RoadReady Expansion Module ![](img/roadready-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}<br>User Manual

## Overview

The [RoadReady Expansion Module](https://www.iascaled.com/store/CKT-XING-TXM) (CKT-XING-TXM) adds support for one or two additional tracks with full approach logic. It is compatible 
with both the RoadReady Basic and the RoadReady Pro.  For supporting even more tracks, RoadReady Expansion Modules can be chained together for an unlimited number of tracks.

NOTE:  If you just want to add more "island" detectors to a RoadReady Basic, you do not need an Expansion Module.  All you need to do is add additional TrainSpotters as described in the [section of the manual](../../Basic Crossing/manual/#additional-detectors).

![](img/ckt-xing-basic.jpg)

### Features

* Indepedent approach logic for one or two tracks
* Plug-and-play detector connections - no fiddly terminal blocks!
* Rock solid TrainSpotter optical detection - works in any ambient lighting conditions
* Configurable approach timeout
* Configurable turn-off delay after detectors clear
* Can be chained together for unlimited additional tracks
* Includes control board, four (4) TrainSpotter optical detectors, and wires
* Compatible with RoadReady Basic and Pro

---

## Quick Start Guide

### Step 1 - Power

Mount the module to the layout and connect the 4-wire cable from either of the "Crossing Expansion" ports to the RoadReady crossing module.

* For the RoadReady Basic, this will be either of the "Sensor Input" ports.  If both are currently occupied by sensors, one of these sensors may be plugged into the open Crossing Expansion port.
* For the RoadReady Pro or another Expansio Module, this will be the "Crossing Expansion" port

FIXME: (Drawing here showing expansion module to basic, pro, and txm)

![](img/ckt-xing-basic-power.jpg)

### Step 2 - Detectors

Each track will need four TrainSpotters - two for the approach circuits, and two for the island circuit.



Mount one TrainSpotter detector on each side of the crossing.  The detectors
should be located at the point where you want the crossing to start
activating, based on your train speed and local layout conditions.  Use one
eight foot cable with each detector, plugging one end into the detecor
itself, and the other into one of the "SENSOR INPUTS" connectors on the
board.  It does not matter which detector plugs into which jack.

![](img/ckt-xing-basic-inputs.jpg)

If you're not sure exactly when you want your crossing to trigger, you can
leave the detectors unmounted initially and try them in different spots
above the layout.  Just be very careful that none of the electronics touch
anything metal or anything energized, like the track or other wiring, as
this will damage the product.

### Step 4 - Crossing Signals

Crossing signals are available from a variety of vendors to match your
prototype and budget.  Most signals available today are compatible with the
board - they just need to be LEDs and wired as common anode (common
positive).  All signals need current limiting resistors installed, if
they're not already installed from the factory.  For typical ~12V power, a
1k resistor is recommended on each negative lead from each signal. 
(Generally that means 2 - one on the left lights, one on the right lights.)
It can be done with a single 1k resistor on the common positive lead as
well, but this will lead to some unevenness in the lights while they fade
back and forth.

!!! note warning
    **The lack of current-limiting resistors will cause permanent damage to the LEDs in your crossing signals.  Make sure you have them installed!**

Connect the common anode (common positive) lead of your signals into the +V terminal of the "CROSSING SIGNAL OUTPUTS" terminal block.

![](img/ckt-xing-basic-outputs.jpg)

Connect the left and right negative leads - *making sure you have resistors on your signals* - to the L and R terminals.  The exact orientation (left or right) is not important - they're just marked that way to help the user be consistent if so desired.  Some crossings are wired so that all lights blink in the same direction at once, whereas others are wired so that signals on opposite sides of the road blink opposite.  It's entirely up to you.

### Step 5 - Configuration

Set switches A, B, and C to the bell sound you want for your crossing.  See [Configuration Options](#configuration-options).

![](img/ckt-xing-basic-config.jpg)

### Step 6 - Turn Off Delay

Set switches X and Y for the turn-off delay you want.  This is the time between when the
detectors clear and when the crossing shuts down.  See [Configuration Options](#configuration-options).

### Step 7 - Testing

Place your hand in front of one of the detectors.  You should see the red light on the
detector stalk turn on, and the crossing should begin ringing and flashing lights back and forth.  Congratulations on a successful install!

---

## Wiring Diagram

[![](img/ckt-xing-basic-diagram.png)](img/ckt-xing-basic-diagram.png)

---

## Configuration Options

The basic crossing controller has two configuration options:  how long the crossing will stay active after all the detectors are clear, and which bell should be used.  Switches X/Y configure the turn-off delay, and switches A/B/C configure which bell sound will be played.

| X | Y | Turn-off Delay |
|---|---|----------------|
| 0 | 0 | 0.5 seconds | 
| 0 | 1 | 2 seconds | 
| 1 | 0 | 5 seconds | 
| 1 | 1 | 10 seconds | 

| A | B | C | Bell Sound |
|---|---|---|----------------|
| 0 | 0 | 0 | Generic crossing bell | 
| 0 | 0 | 1 | Safetran Mechanical | 
| 0 | 1 | 0 | Safetran Hybrid | 
| 0 | 1 | 1 | US&S Teardrop | 
| 1 | 0 | 0 | Western Cullen Hayes 333 | 
| 1 | 0 | 1 | Western Cullen Hayes 777 | 
| 1 | 1 | 0 | Western Railroad Supply 222 | 
| 1 | 1 | 1 | Reserved / Do Not Use | 

---

## Additional Detectors

Additional [TrainSpotter](https://www.iascaled.com/TrainSpotter) detectors can be connected to cover additional tracks or
to extend the detection distance from the crossing.  These can be wired into
the J6 terminal block.

![](img/ckt-xing-basic-extrainputs.jpg)

Connect the red wire(s) to the +V terminal and the black wire(s) to the GND
terminal.  The white wire(s) connect to the EN terminal.

---


## Open Source 

Iowa Scaled Engineering is committed to creating open designs that users are free to build, modify,
adapt, improve, and share with others.  

The design of the CKT-XING-BASIC hardware is open source hardware, and is made available under the
terms of the [Creative Commons Attribution-Share Alike v3.0 license](http://creativecommons.org/licenses/by-sa/3.0/).

The firmware for the CKT-XING-BASIC is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either [version 3 of the  License](https://www.gnu.org/licenses/gpl.html), or any later version.

Design files can be found in the [ckt-xing](https://github.com/IowaScaledEngineering/ckt-xing) project on GitHub.
