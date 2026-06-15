---
title: Introduction
---
# About the Block Signal Pro Kits ![](../img/simplesig-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}

## Overview

The SimpleSig Block Signal Pro kits provide all the needed parts to apply SimpleSig / MSS-compatible signals to more complex trackwork, such as single or double crossovers between two main tracks.

At the heart of all of the Block Signal Pro kits is a Block Signal Custom board, which comes pre-programmed with firmware supporting signaling for the kit's track configuration.  It will also include a number of TrainSpotter infrared detectors and ATOM DCC block detectors based on the kit's needs, as well as plug-and-play cables to interconnect them.  More complex kits may also include Block Signal Custom expansion boards to increase the number of MSS ports, sensor inputs, or signal heads to the number needed for that track configuration.

## Kits Available

* [Single / Double Crossover](./xover.md)
* Automatic Interlocking *(coming soon)*


---

## Specifications

**Input Power:**  8 to 24 volts DC, AC, or DCC  
**Input Supply Current:** Lots of milliamps (typical)  
**MSS Standard Compatibility:** 1.x, 2.x, and (proposed) 3.x  (see note 1)  
**Size:**  5.25"(L) x 5.0"(W) x 0.5"(H) (main and expansion boards)

Note 1:  The diverging approach line on the MSS-XCADE hardware is active low and pulled high.  This means it's only compatible with the draft MSS 3 specification, and not compatible with MSS 2.x implementations of diverging approach.

---

## Open Source 

Iowa Scaled Engineering is committed to creating open designs that users are free to build, modify,
adapt, improve, and share with others.

The design of the MSS-XCADE hardware is open source hardware, and is made available under the
terms of the [Creative Commons Attribution-Share Alike v3.0 license](http://creativecommons.org/licenses/by-sa/3.0/). 
Design files can be found in the [mss-xcade](https://github.com/IowaScaledEngineering/mss-xcade) project on 
GitHub.

