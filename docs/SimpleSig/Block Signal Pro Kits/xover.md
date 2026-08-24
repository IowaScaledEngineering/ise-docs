---
title: Single/Double Crossover
---
# Block Signal Pro - Single/Double Crossover Kit ![](../img/simplesig-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}

## Overview

The SimpleSig Block Signal Pro Single/Double Crossover Kit contains all the needed parts to signal a single or double crossover between two main tracks with SimpleSig / MSS-compatible signals.

The kit includes:

* Block Signal Custom board with Block Signal Pro firmware
* 4x TrainSpotter infrared detectors
* 6x ATOM DCC block detectors
* 10x 8-ft. 3-wire sensor cables

---

## Supported Track Configurations

The Single/Double Crossover Kit supports the following different track configurations.  Please refer to the [Reading the Diagrams](common.md#reading-the-diagrams) section of the common documentation for details on what all of the elements of the diagram mean.

### Standard Single Crossover

For most single crossovers, this is the recommended configuration.  It requires two plant blocks, one for each mainline between the signals.  This assures optimal detection throughout the plant.  

Select "Single Crossover" from the Predefined Configuration list.

[![](img/single-xover-standard.png)](img/single-xover-standard.png)

### Simplified Single Crossover

For very short single crossovers, or for cases where cutting in two plant blocks (one for each main) is not feasible for whatever reason, an alternate configuration can be used as shown below.  This has the disadvantage that it can "lose" short trains - those shorter than the distance from the optical sensors to the gaps in the center of the crossover - and may return a false clear signal.  That's why it's only recommended for very short crossovers.

Select "Single Crossover" from the Predefined Configuration list.

[![](img/single-xover-short.png)](img/single-xover-short.png)


### Standard Double Crossover

For most North American-style double crossovers, this is the recommended configuration.  It requires two plant blocks, one for each mainline between the signals.  This assures optimal detection throughout the plant.

Select "Double Crossover" from the Predefined Configuration list.

[![](img/double-xover-standard.png)](img/double-xover-standard.png)

### Compact Double Crossover

In extremely tight spaces, a "compact double crossover" may be used that has a diamond at the center.  These are far more common in passenter terminal yard throats or on interurban / light rail systems than they are on mainlines, due to the maintenace headaches and cost of the diamond in the middle.  Europe also uses them significantly more often due to space constraints.  

They show up on model railroads with some frequency, and the support for them is only a minor modification to the standard double crossover.  To use these, select "Double Crossover" from the Predefined Configuration list, and then be sure to enable the ["Compact Double Crossover"](#compact-double-crossover-option) in the configuration.

[![](img/double-xover-compact.png)](img/double-xover-compact.png)

### Simplified Compact Double Crossover

Track-wise, this is the same as the Compact Double Crossover.  It eliminates the two plant blocks, however, for cases where isolating those pieces of track is not feasible, or where the double crossover is extremely compact.  This has the disadvantage that it can "lose" short trains - those shorter than the distance from the optical sensors to the gaps in the center of the crossover - and may return a false clear signal.  That's why it's only recommended for extremely short crossovers, and even then, I recommend increasing the [IR sensor off delay](#ir-sensor-off-delay).

To use these, select "Double Crossover" from the Predefined Configuration list, and then be sure to enable the "Compact Double Crossover" in the configuration.

[![](img/double-xover-compact-simple.png)](img/double-xover-compact-simple.png)

### Notes

Note that all of these supports direction inputs from each individual turnout.  This is most prototypical, since a real signal system would verify that each turnout is aligned properly before displaying clear signals, and prevents the case where an operator throws one and forgets to throw the other.  If your turnouts are tied such that they only throw as pairs, you can wire both inputs to one turnout's contacts or the other.

Your crossover may look different than pictured - it might be flipped or rotated.  However, just rotate the diagram until it lines up with how your track looks, and connect appropriately.

---

## Quick Start Guide

To get started, follow the common [Quick Start Guide](common.md#quick-start-guide).  

### Configuration

To get started on initial configuration, again please refer to the common instructions for [Initial Configuration](common.md#initial-configuration).  When you reach the section about configuration, select either "Single Crossover" or "Double Crossover" from the Predefined Configurations as appropriate.  Otherwise, all of the rest of the common configuration instructions apply.

!!! info "Start with Defaults!"
    Defaults are there for a reason.  I highly recommend just starting with the defaults first, since then you have a known baseline configuration.  You can then go in and change settings one at a time and then hitting save,  allowing you to make sure each change is exactly what you want.

### Specific Configuration Options

#### Approach Lighting

If enabled, Approach Lighting will cause signals to be dark until a train is within one block of the interlocking plant.  By default, all signals are constant-lit.

#### 2 Block Approach Lt

If Approach Lighting is turned on, normally signals will only light when something is detected within one block of the interlocking plant.  If "2 Block Approach Lt" is enabled, any occupancy with two blocks of the plant will light the signals.

Note that this just modifies the behavior of "Approach Lighting".  If approach lighting is not selected, the signals will be constant lit regardless of how the two block option is set.

#### Compact Double Crossover Option

(Double Crossover Only)  If using a Compact Double Crossover, enable this option.  This will cause signals to display stop if both crossover routes are lined at the same time.

#### Invert Turnout X Input

Normally, the board expects a given turnout position GPIO input to be grounded if the turnout is set diverging/reverse.  Using these controls, you can invert this behaviour for any or all turnouts, so that the GPIO is grounded if the turnout is set normal/straight.  This accomodates cases where your switch machine contacts may be set up backwards of what the board expects and it's hard to change them.

#### IR Sensor Off Delay

Many applications benefit from some additional delay between when the IR sensor last detects something to when it reports as "off".  This can often fix cases where you get brief invalid signal indications because it's lost track of the cars.  

This slider allows you to add a variable turn-off delay to the IR sensors.  5 seconds is usually a good starting value.
