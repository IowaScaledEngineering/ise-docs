---
title: Introduction
---
# Receiver ![](../img/pt-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"} Setup & Troubleshooting 

## Introduction

First:  ***Yes, you need a receiver.***

The ProtoThrottle uses an industrial 802.15.4 radio for communications reliability.  While it's the same 2.4GHz band as WiFi and other radios, it's a different protocol.  The receiver handles the radio communication with the throttle, and the translation between the ProtoThrottle's protocol and whatever the command station needs.

One receiver is - in theory - capable of handling up to 26 throttles.  The real capacity depends upon the connection to the DCC system and how much traffic it can handle before it gets clogged up.  For NCE/Lenz receivers, the realistic limit is 3-5 in heavy switching use  and 6-8 in road service.  For the WiFi receiver, the limit is maybe 2-3 into an LNWI, 10 or so into an ESU system, and up to almost unlimited with a proper JMRI setup.

!!! question "Why not JMRI WiFi Throttle?"
    Many people have wondered over the years, why doesn't the ProtoThrottle
    use WiFi and the Withrotlee protocol directly?  That's a fair question
    and the answer can be quite involved, but it basically comes down to
    reliability and user experience.  The radio protocol used by the
    ProtoThrottle is a highly robust, resilient system designed for reliable
    communication in adverse conditions, and is very power-efficient.  That, combined with the desire for
    plug-and-play operation of the ProtoThrottle in as many use cases as
    possible, drove the initial design decisions to use a receiver as the
    intermediary.


## Choosing the Correct Receiver

The ProtoThrottle interfaces to almost any DCC system using one of our receivers.  This receiver converts the wireless signal from the ProtoThrottle into the specific protocol required by each command station.  Pick the correct receiver type based on your command station from the table below.

| Brand | Model       | Receiver    | Protocol |
| ----- | ----------- | ----------- | -------- |
| NCE   | Power Pro   | [MRBW-CABBUS](cabbus.md) | Cab Bus |
| NCE   | Power Cab   | [MRBW-CABBUS](cabbus.md) | Cab Bus |
| Lenz  | LZV100      | [MRBW-CABBUS](cabbus.md) | XpressNet |
| ESU   | CabControl  | [MRBW-WIFI](wifi.md) | ESU Proprietary |
| ESU   | ECoS        | [MRBW-WIFI](wifi.md) | ESU Proprietary |
| TCS   | CS-105      | [MRBW-CABBUS](cabbus.md) via AUX port | Cab Bus |
| Digikeijs | DR5000  | [MRBW-CABBUS](cabbus.md) | XpressNet |
| Digitrax | Any      | [MRBW-WIFI](wifi.md) - also requires [LNWI](http://www.digitrax.com/products/wireless/lnwi/) module* | LNWI |
| MRC   | Prodigy     | [MRBW-WIFI](wifi.md) - also requires [Prodigy WiFi](https://www.modelrectifier.com/Prodigy-WiFi-s/332.htm) module* | WiThrottle |
| CVP   | EasyDCC     | [MRBW-WIFI](wifi.md) with JMRI (Example from [The Hills Line](https://thehillsline.com/2020/03/05/fahrvergnugen/)) | WiThrottle |
| Other |             | If it's compatible with JMRI, you can interface to it by running JMRI (requires computer running JMRI and appropriate interface to your DCC system) and connecting via the [MRBW-WIFI](wifi.md) interface.  JMRI hardware support can be checked [here](http://jmri.sourceforge.net/help/en/html/hardware/index.shtml). | WiThrottle |

*Note: If you already have a working JMRI installation with WiThrottle server, then the LMWI (Digitrax) or Prodigy WiFi (MRC) module is not required.  In that case, connect the MRBW-WIFI to the WiThrottle server using the same settings you would use to connect a cell phone throttle.

