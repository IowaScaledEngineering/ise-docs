---
title: User Manual
---
# ARD-LTC2499 v2.0 User Manual 

## Overview

The ARD-LTC2499 is an Arduino-compatible shield that contains a Linear Technology LTC2499 24-bit ADC coupled with an LT6654 precision voltage reference. It is capable of converting 16 single-ended channels, 8 differential channels, or any other combination. In addition to measuring voltage, the ADC can interface directly to a variety of sensors including strain gauges, thermocouples, and current shunts. The onboard EEPROM can be used to store calibration and configuration information directly on each ARD-LTC2499 board. A 6-byte EUI-48-compatible globally unique ID number is also provided. The ARD-LTC2499 can be used with other Arduino shields to make a simple, yet very accurate, data acquisition system.

Note: The normal ARD-LTC2499 is not compatible with Arduinos using 3.3V I/O on the I2C lines, such as the Due, Zero, etc. This is because the LTC2499 requires a 5V supply to deal with the 4.096V reference voltage, making it incompatible with 3.3V I2C. A 3.3V compatible version is available as the ARD-LTC2499-3V3, which is identical except that it also includes on-board level shifters for the I2C lines.


![](img/mss-atlasadapter.jpg)

### Features

* Precision 24-bit delta sigma ADC in an Arduino-friendly form factor
* 16 single-ended channels, 8 differential channels, or any combination
* 7.5 samples/sec (or 15 samples/second without automatic offset cancellation)
* Input common mode voltage range of -0.3V to 5.3V
* Input measurement range of 0-2.048V (single-ended) or -2.048V to 2.048V (differential)
* 4.096V LT6654 precision voltage reference on board
* Optional onboard 5V linear regulator provides clean power to the ADC and reference
* 128 bytes of onboard EEPROM for storing configuration or calibration values
* Read-only 6-byte EUI-48-compatible globally unique ID
* Arduino software library for easy use
* 5V compatible I2C interface (or 3.3-5V with the ARD-LTC2499-3V3)


### Typical Applications

* Expand your existing Atlas signal system installation using using standard ISE SimpleSig or other Modular Signal System-compatible modules

---

## Quick Start Guide

!!! warning "Turn The Power Off!"
    All wiring and setup of the board should be done with the power off.  This significantly reduces the chances of accidentally slipping and causing a short circuit that damages the board, the block detectors, or the signals.

!!! info "Please Note"
    Since the wiring nomenclature gets a bit confusing in terms of directions, looking at the wiring diagram below is highly recommended rather than just relying on the text.

### Step 1 - Power
 The Atlas Adapter needs 6V to 24V of DC, AC, or DCC power, and it must be the same power supply that is used to power the Atlas modules, since the Atlas signal bus does not carry a ground wire.  Connect power to the terminals marked "POWER" on the PCB.

![](img/mss-atlasadapter-power.png)

---

### Step 2 - Atlas Upstream
Connect J1 on the Atlas Adapter board to J2 on the last Atlas Universal Signal Control Board (USCB) for signals headed away from the connection point, as shown in blue below.  Connections should be made with standard 4 or 6 wire, "straight through" RJ11 cables, same as is used to connect the Atlas USCB modules.

![](img/mss-atlasadapter-step2.jpg)

---

### Step 3 - Atlas Downstream
Connect J2 on the Atlas Adapter board to J2 to J1 on the last Atlas USCB for signals headed towards the connection point, as shown in blue below.  Connections should be made with standard 4 or 6 wire, "straight through" RJ11 cables, same as is used to connect the Atlas USCB modules.

![](img/mss-atlasadapter-step3.jpg)

---

### Step 4 - MSS
Using the provided short RJ45 cable, connect the adapter board's MSS port to the next MSS signal module as shown below in orange.  (Note that this is a normally-wired network cable and not a crossover cable normally used with MSS.) 

![](img/mss-atlasadapter-step4.jpg)

---

## Simplified Wiring Diagram

[![Simplified Wiring Diagram for Atlas-MSS System](img/atlas-mss-wiring-diagram.png)](img/atlas-mss-wiring-diagram.png)
[Simplified Wiring Diagram for Atlas-MSS System](img/atlas-mss-wiring-diagram.png)

!!! info "Block Detector Placement"
    Please note that the current-based block detector for the block between Atlas USCB board 3E and MSS signal board 4 on the diagram should be attached to Atlas USCB 3E, as shown in the full diagram above.  The MSS board does not need a detector for that block, and will get that block's occupancy through the Atlas Adapter connection.

---

## Diagnostic LEDs

For describing the purpose and meaning of the diagnostic LEDs on the board, we'll use the [Simplified Wiring Diagram](img/atlas-mss-wiring-diagram.png) from above as a reference.  Each of the Atlas and MSS boards is numbered.  Atlas boards along the bottom will be described as "eastbound" and carry a #E designation, meaning a train moving from left to right (or east if this were a map) would be seeing those signals.  Atlas boards along the top will be described as "westbound" and carry a #W designation, meaning a train moving right to left (or west if this were a map) would see signals controlled by those boards.

![](img/mss-atlasadapter-diag-leds.png)

| Direction | LED&nbsp;Name/Color | If Indicator is On |
|-------------------|--------------------|-----------------|
| Atlas->MSS | *ADV APRCH*<br/>Blue (D11) | The Atlas USCB 3W on [the diagram](img/atlas-mss-wiring-diagram.png) is sending an "advance approach" indication to MSS, indicating that it is currently displaying an approach indication and the Atlas USCB 2W is displaying a stop indication for westbound trains. | 
| Atlas->MSS | *APRCH*<br/>Amber (D8) | The Atlas USCB 3W is sending an "approach" indication to MSS, indicating that it is currently displaying a stop indication for westbound trains. | 
| Atlas->MSS | *CURR BLOCK*<br/>Red (D7) | The Atlas USCB 3E is sending occupancy for the block detector connected to it that covers the block between it and the first MSS signal. | 
| MSS->Atlas | *APRCH*<br/>Amber (D8) | MSS Cascade module 4 is sending that it is displaying a stop indication, and that it expects the right-most bottom (eastbound) Atlas module to display an approach indication. | 
| MSS->Atlas | *ADV APRCH*<br/>Amber (D8) | MSS Cascade module 4 is sending that it is displaying an approach indication, and that it expects the right-most bottom (eastbound) Atlas module to display an advance approach indication if 4-aspect signaling is enabled, or green if only 3-aspect signaling is enabled. | 

---

## Specifications

**Input Power:**  5 to 24 volts DC, AC, or DCC  
**Input Supply Current:**  30 milliamps @ 12V (typical)  
**MSS Standard Compatibility:** 1.x, 2.x, and (proposed) 3.x  
**Size:**  2.75"(L) x 2.5"(W) x 0.5"(H)  

---

## Open Source 

Iowa Scaled Engineering is committed to creating open designs that users are free to build, modify,
adapt, improve, and share with others.

The design of the MSS-ATLASADAPTER hardware is open source hardware, and is made available under the
terms of the [Creative Commons Attribution-Share Alike v3.0 license](http://creativecommons.org/licenses/by-sa/3.0/). 
Design files can be found in the [mss-atlasadapter](https://github.com/IowaScaledEngineering/mss-atlasadapter) project on 
GitHub.

