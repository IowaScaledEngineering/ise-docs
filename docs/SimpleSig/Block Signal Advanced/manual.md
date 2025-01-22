---
title: User Manual
---
# Block Signal Advanced User Manual ![](../img/simplesig-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}

## Overview

The Iowa Scaled Engineering [Block Signal Advanced](https://www.iascaled.com/store/MSS-CASCADE-ADVANCED) is a complete solution for adding ABS block signals at a track block boundary.  It is more capable than our Block Signal Basic, able to display configurable aspects on single or double-headed signals.

It is fully compatible with the [Modular Signal System (MSS)](../index.md) standards, and provides what the MSS standard calls a "cascade."

![](img/mss-cascade-adv.png)


### Features

* Complete ABS-style signaling solution for a block boundary
* Compatible with Modular Signal System standards 1.x, 2.x, and (proposed) 3.x
* Controls one LED block signal with one or two signal heads in each direction
* Powered from 8V to 24V DC, AC, or DCC power.
* Compatible with both common anode (positive) and common cathode (negative) signals
* Realistic signal fading during changes for both tri-light and searchlight style signals
* Supports both always-on signals and approach lighting
* Configurable aspects for each indication MSS is capable of displaying
* Supports stop, approach, advance approach, approach diverging, approach diverging with advance approach, and clear indications
* Simple plug-and-play compatibility with most Atlas HO and N scale signals
* Includes control board, ATOM DCC block detectors and one TrainSpotter optical detector

### Typical Applications

* Add operating ABS-style block signals at a block boundary where more advanced indications are needed, such as at the signal before a complex cascade where approach diverging aspects need to be displayed
* Perfect for locations where non-standard aspects are needed, such as the ability to display restricting at the end of ABS
* Great for easily signaling home layouts as well as Free-Mo and Free-MoN modules
---

## Quick Start Guide

!!! warning "Turn The Power Off!"
    All wiring and setup of the board should be done with the power off.  This significantly reduces the chances of accidentally slipping and causing a short circuit that damages the board, the block detectors, or the signals.

[![Simplified Wiring Diagram for Block Signal Advanced](img/mss-cascade-adv-wiring-diagram.png)](img/mss-cascade-adv-wiring-diagram.png)
[Simplified Wiring Diagram for Block Signal Advanced](img/mss-cascade-adv-wiring-diagram.png)

### Step 1 - Signals

!!! info "Common Anode vs Common Cathode"
    The Block Signal Advanced supports both common anode (positive) and common cathode (negative) signals, but all of the signals connected must be of one type or the other.  Mixing common anode and common cathode signals on the same Block Signal Advanced is not supported.

Most applications will want to use two signals - one facing each way at the block boundary.  These signals can be either single or double-headed, depending on the need.  The Block Signal Advanced comes set up by default for both signals to be double-headed, but can be configured to operate a single-headed signal in either (or both) directions.  Double-headed signals will be most appropriate for the signal one block ahead of the point end of a switch (such as would be controlled by the [Switch Signal Basic](../Switch Signal Basic/manual.md)), but can be used in other situations depending on the prototype.  

If using a single-headed signal, connect it to the upper head port.

LED signals with the usual red/yellow/green leads can be wired into the terminal blocks.  The common wire should be connected to the terminal block labeled **SIGNAL COMMON**, and the individual color leads should be attached to the respective **R** (red), **Y** (yellow), and **G** (green) positions on the **SIGNAL A UPPER**, **SIGNAL A LOWER** (if needed), **SIGNAL B UPPER** and **SIGNAL B LOWER** (if needed) terminal blocks.

![](img/mss-cascade-adv-signal-terminals.png)

If you are using signals from Atlas, they will plug directly into the off-white connectors marked **SIGNAL A UPPER**, **SIGNAL A LOWER** (if needed), **SIGNAL B UPPER** and **SIGNAL B LOWER**.  If the signal leads aren't long enough to reach the main board, Iowa Scaled Engineering offers [extension cables](https://www.iascaled.com/store/ACC-ATLASEXT).

![](img/mss-cascade-adv-signal-connectors.png)

Set the **COMMON** switch to **ANODE / +** if your signals are common anode / common positive (this is most common).  Likewise, set the switch to **CATHODE / -** if your signals are common cathode / common negative.

![](img/mss-cascade-adv-cacc-switch.png)

The Block Signal Advanced powers the signals from 5 volts and has 330 ohm resistors on each of the signal outputs to protect the signal LEDs, so no additional resistors are needed externally.  If your signals are too bright with the built-in resistors, additional resistors can be added to each of the signal output lines.  If your signals already have resistors built in, you will likely need to remove them or disable the onboard resistors.  See [Bypassing the LED Resistors](#bypassing-the-led-resistors) in the Advanced Use Cases section below.

---

### Step 2 - ATOM Detectors

Based on your installation, you will need one or two ATOM DCC current-based block detectors.

For modular setups, one ATOM detector is required on each block of track - A and B.  The rail connected through the detector must be isolated at the track block boundary, which should be located right at the signals.

For home layout use, only one ATOM current-based block detector is needed per track block if the block rails are electrically continuous between signals.  It can be connected to the signal module at either end of the block depending on what is convenient, but each block should have one and only one ATOM detector.

All of the feeders for the detected rail in a block must pass through the current transformer in the ATOM block detector as shown below.  Only make one pass through the transformer, and only pass the feeders to one rail through it.  Making multiple turns around the transformer or passing both sets of feeders through will cause the detector to not work properly.

![](img/bd1-wiring-small.png)

Install ATOM detectors as needed and use the included 8 foot cables to connect them into the **BD1 A** and **BD1 B** inputs on the main board as appropriate.

![](img/mss-cascade-basic-bd-connections.png)

---

### Step 3 - TrainSpotter Detector ![](img/ckt-irsense-installation.png){align=right style="width:20%; margin-left:20px; margin-bottom:10px"}

!!! info "Omitting Optical Detection"
    For home layout use, the TrainSpotter may be omitted if all of your cars have resistor-equipped axles and you want to depend entirely upon current detection.  For Free-Mo layouts, the optical detector must be installed for compliance with the standard.

The TrainSpotter provides optical detection.  It should be installed as close to the block boundary at the signals as possible.  Use one of the included 8 foot cables to connect the TrainSpotter to the **IR SENSOR** connector.

![](img/mss-cascade-basic-ir-connections.png)

---

### Step 4 - Connect Power

The Block Signal Advanced requires 8V to 24V of DC, AC, or DCC power to operate.  Connect power to the board using the terminal block labeled **POWER**.  It can be powered directly from the FreeMo accessory bus on modular setups.

For home setups, it is recommended to power it from an accessory power bus, but it can be powered from the track bus directly (but before any block detectors, otherwise the current draw of the board will activate the block detector).  Note: all signal modules need to get their power from the same power source.

![](img/mss-cascade-adv-power.png)

---

### Step 5 - Initial Testing

Do not connect any MSS cables yet!  First we're going to make sure that the Block Signal Advanced is connected correctly.

Apply power and check that the green power LED glows on the Block Signal Advanced and any attached ATOM current-based block detectors.  Assuming nothing on the track, the signals should both display green.

Place your hand over the TrainSpotter sensor.  Verify the red light on the sensor comes on and both signals drop to red over red (or just red for single-headed signals).  Remove your hand and verify both return to green over red (or just green).  (If this is a home setup with no TrainSpotter sensor installed, skip this step.)

Turn on track power and make sure nothing is in either of the track blocks and that the red detection LED is OFF on all detectors (ATOMs and the TrainSpotter).  If any ATOMs show detection, very carefully check that the track blocks are correctly isolated and there is nothing on the track.  If you are absolutely sure of this, you may need to [run a self-calibration on that ATOM](../../ATOM%20Block%20Detector/manual.md/#operation) to cancel out leakage current.  If a calibration is run and the red detection light does not go off, you almost certainly have a wiring error in your DCC track wiring with that detector.

With track power still on, place a locomotive on the block in front of the A end signal.  Verify that the ATOM detector shows detection (red light) and that the B end signal drops to red over red (or just red if using a single-headed signal).  Remove the locomotive and verify that approximately ~3 seconds later, the red light on the ATOM detector goes out and the B signal returns to green over red (or just green).  Repeat the process by placing the locomotive in front of the B signal and verify the B block detector triggers and that the A signal drops to red.  This will verify that your detectors are properly tuned and connected.

Congratulations!  You've now successfully installed and verified your Block Signal Advanced!

---

### Step 6 - Connect MSS

Now in order for the signals to interoperate with other SimpleSig or Modular Signal System-compatible products, you need to connect each signal module to the next via crossover cables.  **The golden rule of the Modular Signal System is that there must be an odd number of "crossovers" between signal boards.**

For home layouts, this typically means you should connect one signal board to the next using a single "crossover" cable of appropriate length.  Those can be purchased from a number of sources, including ISE, or you can make your own if you're comfortable with crimping ends on networking cable.

For modular layouts, it's generally recommended that except for very short modules, "straight through" (normal) ethernet cables should be used from the signal board to the ends of the module, where the signal bus terminates at a coupler or jack.  The modules then get joined together using crossover cables. 

For more information about crossover cables, be sure to see the [Tips and Tricks page](../tips.md).

If you do not have any more signal boards in a given direction down the track, just leave the connector open.

![](img/mss-cascade-basic-mss-connections.png)

---

## Options

The Block Signal Advanced has five configuration option switches.

![](img/mss-cascade-adv-option-switches.png)

### Switch A - Approach Lighting

By default, the Block Signal Advanced keeps both signals lit at all times.  Some prototype signals are only lit when a train is approaching the signal, a feature appropriately enough called "approach lighting."  If you want your signals to only be lit only when a train is occupying either adjacent block and dark otherwise, set switch A to on.

### Switch B - Reserved

Switch B is reserved for new features and future enhancements to the firmware.

### Switch C - Searchlight Emulation

By default (switch C is OFF), the Block Signal Advanced is set up to emulate the operation of typical signal heads with three independent sets of lights, arranged either vertically or in a triangle configuration on most railroads.  (Or, in the case of Pennsylvania position lights or B&O/N&W color position lights, drive two lights around the outside of a disk.)  Regardless, the logic will fade one in as the other fades out.

Searchlight-type signals, such as the Union Switch & Signal types H, H2 and H5 as well as the General Railway Signaling SA type, used a signal lamp with a set of mechanically-changed color filters inside known as roundels.  Three roundels were mounted on an armature that could be moved by two electromagnetic coils.  When unenergized, the arm sat in the middle and placed the red filter in front of the single lamp.  Green would be on one side, and yellow on the other side.  By energizing the coils, it would pull the arm either left or right and place either yellow or green in front of the lamp.

This leads to interesting effects when changing aspects.  When going between yellow and green, you'll get a couple quick red flashes as the armature moves from one side through the red glass in the center to the other side, and then usually bounces once or twice.  Going from red to either yellow or green will result in a bit of flickering as well as the armature bounces around before settling.  The Block Signal Advanced emulates this rather precisely.  If Switch C is ON, this bouncing and flashing will be reflected in the signal output giving a very prototypical appearance to model searchlight signals.

### Switch D - Reserved

Switch D is reserved for new features and future enhancements to the firmware.

### Switch E - Configuration Mode

Normally, switch E should be kept in the OFF position.  To enter configuration mode, switch E will be turned ON.  See [Programming Signal Aspects] below for more details.

---

## Programming Signal Aspects

One of the best features of the Block Signal Advanced is the ability program the specific signal aspects for each signal for each condition that MSS is capable of sending.

In order to unlock configuration mode, set switch E to ON.  The mock signal in the middle of the board should light up, as well as a blue LED indicating whether the A or B signal is being configured and a yellow LED indicating which condition is being configured.

The Block Signal Advanced supports six potential conditions, as listed below, along with their default upper and lower head aspects.

| Condition    | MSS Lines        | Upper  | Lower |
| ------------ | ------------------ | ------ | ------ |
| Stop (S)     | S=1 A=X AA=X AD=X  | Red    | Red    |
| Approach (A) | S=0 A=1 AA=X AD=0  | Yellow | Red    |
| Advance Approach (AA) | S=0 A=0 AA=1 AD=0  | Fl Yellow | Red    |
| Approach Diverging & Advance Approach (AD+AA) | S=0 A=X AA=1 AD=1  | Yellow | Yellow    |
| Approach Diverging (AD) | S=0 A=X AA=0 AD=1  | Yellow | Yellow    |
| Clear (CLR) | S=0 A=0 AA=0 AD=0  | Green | Red    |

Note:  MSS Lines indicates the logical state of the MSS signal wires on the bus.  A **1** indicates the line is logically true/active (typically near ground).  A **0** indicates the line is logically false/inactive (floating or near 12V).  An **X** indicates that it doesn't matter and that line can be in any state.

To change which signal is being configured (A or B), press the left button under the **SIGNAL  A/B** lights, and the blue light should switch between signal A and B.

![](img/mss-cascade-adv-signal-switch.png)

To change which condition is being configured, push the right button under the various yellow condition LEDs until the one you want to configure is lit.

![](img/mss-cascade-adv-signal-state-switch.png)

Once you have selected the signal and the condition to be set, push the buttons next to the two heads on the board until the aspect you want appears.  The upper button cycles the upper head and the lower button cycles the lower head.  Aspects will cycle through red, flashing red, yellow, flashing yellow, green, flashing green, and dark for each press of the button.  Changes are saved immediately.

![](img/mss-cascade-adv-signal-heads.png)

Once you have configured each condition and signal the way you want it, set switch E back to OFF in order to prevent accidental changes.  The configuration LEDs should turn back off.

### Example Signal Options

The aspects programmed in from the factory are generally appropriate for most western US railroads approaching the point-end of a control point.  Let's look at some reasons you may want to change these.

Eastern US railroads often used yellow over yellow for advance approach rather than flashing yellow over red.  Likewise, they often used yellow over green for approach diverging.

Some prototypes with higher speed mainline turnouts used yellow over green or yellow over flashing green on the approach signal to indicate that the turnout was thrown diverging, but that a higher speed was authorized on the diverging route.  However, in those cases, if the signal two blocks down was set to stop (meaning both approach diverging and advance approach are set), you may only want to show a regular approach diverging indication (yellow over yellow) to still warn crews that they should be prepared to slow by the next signal.

Given that prototype sidings are usually multiple blocks apart, it's quite typical that only a signal direction will have a double-headed signal.  Only the direction headed towards the switch would need to display indications giving crews notice of whether they were about to enter the diverging route.  The signal going in the other direction may not have another switch for several blocks and thus would only need the indications that are possible to display on a single signal head.  If all four indications are desired (stop, approach, advance approach, clear), then just connecting that to the upper head outputs works fine.  However, if you want only three indications, you could configure the upper head to show green in the case of advance approach.

Other railroads didn't use double headed signals at all on the approach to sidings.  Some roads would use a single-headed signal, and just display a flashing yellow for both advance approach and for approach diverging.

At the end of signaled track, particularly where the main line terminates into a yard, it's typical to put a restricting indication.  The exact behavior depends upon the railroad rulebook, but typically this is a flashing red over red that tells a crew they need to be down to restricted speed (be able to stop in half the available sight distance) but they don't actually need to stop at the signal.  The Block Signal Advance could easily be configured to display that indication instead of stop, and by putting permanent detection on that side of the block boundary, that indication would trickle back to approaching signals as well.







### Factory Reset

To reset all signal configurations to factory default, make sure switch E is off.  Then hold down both the left and right buttons and, while keeping them held, flip switch E to on.  Wait one second, release both buttons and set switch E back to off.  This will restore the default configuration for all signal indications.


---

## Advanced Use Cases

### Bypassing the LED Resistors

The Block Signal Advanced includes resistors to protect your signals against excessive current that will destroy them.  There may be use cases where your signals already have resistors installed, or you want to change the resistor values used, and you need to bypass the resistors on the board.  There are solder jumpers provided to let you do that, but be **very sure** that you know what you're doing before using them.

!!! warning "Don't Destroy Your Signals!"
    Be sure you really need to do this before even considering bypassing the onboard current limiting resistors for the signals.  You must install external resistors before bypassing the onboard resistors, or the current will blow up your signal LEDs!

JP1-JP3 bypass the resistors for Signal A red, yellow, and green respectively.  JP4-JP6 bypass the resistors for Signal B red, yellow, and green, respectively.

If you just wish to dim your signals further, we recommend adding additional resistance between the terminal block and the signal, and leaving the onboard resistance alone.  Then, if for some reason your external resistor gets shorted or you forget to put one in, your signal is still protected against overcurrent that will destroy the LEDs.

---

## Specifications

**Input Power:**  8 to 24 volts DC, AC, or DCC  
**Input Supply Current:**  75 milliamps (typical)  
**MSS Standard Compatibility:** 1.x, 2.x, and (proposed) 3.x  
**Size:**  3.25"(L) x 3.0"(W) x 0.5"(H) (main board)

---

## Open Source 

Iowa Scaled Engineering is committed to creating open designs that users are free to build, modify,
adapt, improve, and share with others.

The design of the MSS-CASCADE-BASIC hardware is open source hardware, and is made available under the
terms of the [Creative Commons Attribution-Share Alike v3.0 license](http://creativecommons.org/licenses/by-sa/3.0/). 
Design files can be found in the [mss-cascade](https://github.com/IowaScaledEngineering/mss-cascade) project on 
GitHub.  Because the MSS-CASCADE project contains multiple types of block signal modules, look in the mss-cascade-basic directories when available.

The firmware for the MSS-CASCADE-BASIC is free software: you can redistribute it and/or modify it under the 
terms of the GNU General Public License as published by the Free Software Foundation, either [version 3 of the 
License](https://www.gnu.org/licenses/gpl.html), or any later version.
