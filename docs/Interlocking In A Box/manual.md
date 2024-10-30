---
title: User Manual
---
# Interlocking In A Box ![](img/simplesig-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}<br>User Manual

## Overview

The Iowa Scaled Engineering [Interlocking In A Box](https://www.iascaled.com/store/CKT-IIAB)
is a complete solution for signaling a simple automatic interlocking
(diamond) where one track crosses another at grade.  It provides all the
necessary sensors and signal logic to drive the signals of your choice on
one operational main track crossing an inactive (dummy) track.

Both a fully automatic and a manual interlocking can be simulated with the
Interlocking In A Box.  With an automatic interlocking, sensors detect the
arrival of a train on the approach to the diamond.  If the diamond is not
already occupied, or once it becomes unoccupied, the approach signal turns
green allowing the train to cross the diamond.

With a manual interlocking, an approaching train is not automatically
detected.  On the prototype, to cross the diamond the conductor must press a
button in a trackside box or, in some cases, manually operate a gate
protecting the diamond.  In the model railroad world, this action can be
replicated with pushbuttons on the fascia, indicating to the Interlocking In
A Box that a train is waiting to cross the diamond.

!!! note "Please Note"
    The Interlocking In A Box is meant for use with a single operational
    track that crosses an inoperable track at a diamond crossing.  For two
    active tracks crossing each other, look for a future "Pro" version with
    more functionality.

![](img/ckt-iiab.jpg)

### Features

* Simulates a manual or automatic interlocking at a diamond 
* Designed for simplicity and to cover most use cases
* Triggered by either TrainSpotter sensors (automatic interlocking) or pushbuttons (manual interlocking)
* Controls a 2-aspect signal, typically displaying red and green, in each direction
* Optional delay time (fixed or randomized) between arrival and green signal
* Compatible with both common anode (positive) and common cathode (negative) signals
* Realistic signal fading during changes for both tri-light and searchlight style signals
* Simple plug-and-play compatibility with most Atlas HO and N scale signals
* Includes control board and TrainSpotter optical detector(s)
* Powered from 6V to 24V DC, AC, or DCC power.

### Typical Applications

* Automatic interlockings

---

## Quick Start Guide

!!! warning "Please Note"
    All wiring and setup of the board should be done with the power off.  This significantly reduces the chances of accidentally slipping and causing a short circuit that damages the board, the block detectors, or the signals.

**Insert diagram here**

The two approaches to the diamond are called A and B, respectively.  Both
operate identically, but be sure to keep the inputs and outputs consistent
when istalling on the layout.

### Install Signals

Most applications will want to use two signals, one on each approach to the
diamond.  Three aspect signals can be used, but the Interlocking In A Box will
only drive two of the LEDs.  In most cases, this will be red and green.

LED signals with the usual red/green leads can be wired into the terminal
blocks.  The common wire should be connected to the **COM** terminal,
and the individual color leads should be attached to the respective **R** (red)
and **G** (green) positions on the **Signal A** and **Signal B** terminal blocks.

![](img/ckt-iiab-signal-termblk.jpg)

If you are using signals from Atlas, they will plug directly into the
off-white connectors marked **Signal A** and **Signal B**.  If the signal leads
aren't long enough to reach the main board, Iowa Scaled Engineering offers
extension cables.

![](img/ckt-iiab-signal-atlas.jpg)

Set the **COMMON** switch to **ANODE / +** if your signals are common anode /
common positive (this is most common).  Likewise, set the switch to **CATHODE
/ -** if your signals are common cathode / common negative.

![](img/ckt-iiab-commonsw.jpg)

The Interlocking In A Box powers the signals from 5 volts and has 330 ohm
resistors on each of the signal outputs to protect the signal LEDs, so no
additional resistors are needed externally.  If your signals already have
resistors built in, you will likely need to remove them or disable the
onboard resistors.  See the section below.

### Install the Diamond TrainSpotter Detector ![](img/ckt-irsense-installation.png){align=right style="width:20%; margin-left:20px; margin-bottom:10px"}

The TrainSpotter provides optical detection.  One TrainSpotter is always
installed in the diamond to detect when a train crosses the diamond.  Use
one of the included 8 foot cables to connect the TrainSpotter to the
**Diamond** connector on the main board.

![](img/ckt-iiab-sensors.jpg)

### Install the Approach Detectors

#### Automatic Interlocking

For a fully automatic interlocking, install the other two TrainSpotter
detectors at the approaches to the diamond on either side.  These should be
sufficiently in front of each signal to trigger the Interlocking In A Box
before the train reaches the signal.  Use the included 8 foot cables to
connect the TrainSpotter to the **Block A** and **Block B** connectors on
the main board.  Be sure the "A" detector is on the same side of the diamond
as the "A" signal, and similarly for the "B" side.

#### Manual Interlocking

In the case of a manual interlocking, connect pushbuttons (typically mounted
on the fascia) to the **Inputs** terminal block.  One pushbutton for the "A"
approach should connect between the **A** terminal and a **GND** terminal. 
The other pushbutton for the "B" approach connects between the **B**
terminal and the **GND** terminal.

![](img/ckt-iiab-inputs.jpg)

### Connect Power

Connect power to the board - it requires 6V to 24V of DC, AC, or DCC power. 
This power can come from an accessory power bus, or from the track bus
directly (but before any block detectors).

### Initial Testing

Apply power and check that the green power LED glows on the main board. 
This verifies that the Interlocking In A Box is getting good power. 
Immediately after power up, the signals will display both red and green in
sequence.  This is normal and verifies that the signals are connected
correctly.  The status LED on the main board will also flash through a
sequence of color.  Once that finishes, the Interlocking In A Box is ready.

!!! note "Please Note"
    The status LED on the main board provides diagnostic information. 
    Normally, you can ignore this.  But, in the event you need technical
    support, you may be asked for what this LED is displaying.

Place your hand over the TrainSpotter detector on one approach to the
diamond.  Verify the red light on the detector comes on and the signal on
that approach turns green.  Remove your hand and verify that the red light
on the TrainSpotter detector turns off.  Note that the approach signal
should remain green.

Next, place your hand over the diamond TrainSpotter detector.  Verify that
the red light on the detector comes on and the approach signal turns red. 
Remove your hand and verify that the red light on the TrainSpotter detector
turns off.  Wait 20 seconds (or more) before proceeding.

Finally, using the opposite approach, repeat the steps above to verify
correct operation on that approach.

Congratulations!  You've now successfully installed and verified your
Interlocking In A Box!

---

## Options

The Interlocking In A Box allows you to customize some delay times and light
options to suit your prototype and operating needs.  These options are set
using the DIP switches on the main board.

### Delay ![](img/ckt-iiab-delay.jpg){align=right style="width:30%; margin-top:0px; margin-left:20px; margin-bottom:10px"}

**FIX ME**

### Timeout ![](img/ckt-iiab-timeout.jpg){align=right style="width:30%; margin-top:0px; margimargin-left:20px; margin-bottom:10px"}

**FIX ME**

### Searchlight Emulation ![](img/ckt-iiab-searchlight.jpg){align=right style="width:30%; margin-top:0px; margin-left:20px; margin-bottom:10px"}

By default, the Interlocking In A Box is set up to emulate the operation of
typical signal heads with two independent sets of lights.  Or, in the case of
Pennsylvania position lights or B&O/N&W color position lights, drive two
lights around the outside of a disk.  Regardless, the logic will fade one in
as the other fades out.

Searchlight-type signals, such as the Union Switch & Signal types H, H2 and
H5 as well as the General Railway Signaling SA type, used a signal lamp with
a set of mechanically-changed color filters inside known as roundels.  Three
roundels were mounted on an armature that could be moved by electromagnetic
coils.  When unenergized, the arm sat in the middle and placed the red
filter in front of the single lamp.  Green would be on one side.  By
energizing the coil, it would pull the arm to the side and place the green
in front of the lamp.

This leads to interesting effects when changing aspects.  Going from red to
green will result in a bit of flickering as the armature bounces around
before settling.  The Interlocking In A Box emulates this rather precisely. 
If the **SEARCHLIGHT** switch is set to **ON**, this bouncing and flashing will be
reflected in the signal output giving a very prototypical appearance to
model searchlight signals.

---

## Advanced Use Cases

### Bypassing the LED Resistors

The Interlocking In A Box includes resistors to protect your signals against
excessive current that will destroy them.  There may be use cases where your
signals already have resistors installed, or you want to change the resistor
values used, and you need to bypass the resistors on the board.  There are
solder jumpers provided to let you do that, but be **very sure** that you
know what you're doing before using them.

!!! warning "Don't Destroy Your Signals!"
    Be sure you really need to do this before even considering bypassing the
    onboard current limiting resistors for the signals.  You must then install
    external resistors or the current will blow up your signal LEDs!

JP1 and JP2 on the back side bypass the resistors for Signal A red and green
respectively.  JP3 and JP4 bypass the resistors for Signal B red and green
respectively.

If you just wish to dim your signals further, we recommend adding additional
resistance between the terminal block and the signal, and leaving the
onboard resistance alone.  Then, if for some reason your external resistor
gets shorted or you forget to put one in, your signal is still protected
against overcurrent that will destroy the LEDs.

---

## Specifications

**Input Power:**  6 to 24 volts DC, AC, or DCC  
**Input Supply Current:**  100 milliamps @ 12V (typical)  **FIX ME**  
**Size:**  3.75"(L) x 2.25"(W) x 0.5"(H) (main board)

---

## Open Source 

Iowa Scaled Engineering is committed to creating open designs that users are free to build, modify,
adapt, improve, and share with others.

The design of the MSS-SIDING hardware is open source hardware, and is made available under the
terms of the [Creative Commons Attribution-Share Alike v3.0 license](http://creativecommons.org/licenses/by-sa/3.0/). 
Design files can be found in the [mss-siding](https://github.com/IowaScaledEngineering/mss-siding) project on 
GitHub.

The firmware for the MSS-SIDING is free software: you can redistribute it and/or modify it under the 
terms of the GNU General Public License as published by the Free Software Foundation, either [version 3 of the 
License](https://www.gnu.org/licenses/gpl.html), or any later version.
