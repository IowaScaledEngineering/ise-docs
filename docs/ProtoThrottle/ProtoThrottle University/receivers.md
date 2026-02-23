---
title: "Receiver Setup & Troubleshooting"
---
# Receiver ![](img/pt-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}<br>Setup & Troubleshooting 

## Choosing the Correct Receiver

The ProtoThrottle interfaces to almost any DCC system using one of our
receivers.  This receiver converts the wireless signal from the
ProtoThrottle into the specific protocol required by each command station. 
Pick the correct receiver type based on your command station from the table
below.

| Brand | Model       | Receiver    | Protocol |
| ----- | ----------- | ----------- | -------- |
| NCE   | Power Pro   | [MRBW-CABBUS](#nce-cab-bus-and-lenz-xpressnet) | Cab Bus |
| NCE   | Power Cab   | [MRBW-CABBUS](#nce-cab-bus-and-lenz-xpressnet) | Cab Bus |
| Lenz  | LZV100      | [MRBW-CABBUS](#nce-cab-bus-and-lenz-xpressnet) | XpressNet |
| ESU   | CabControl  | [MRBW-WIFI](#esu-cabcontrol-jmri-wifi-throttle-and-digitrax-lnwi) | ESU Proprietary |
| ESU   | ECoS        | [MRBW-WIFI](#esu-cabcontrol-jmri-wifi-throttle-and-digitrax-lnwi) | ESU Proprietary |
| TCS   | CS-105      | [MRBW-CABBUS](#nce-cab-bus-and-lenz-xpressnet) via AUX port | Cab Bus |
| Digikeijs | DR5000  | [MRBW-CABBUS](#nce-cab-bus-and-lenz-xpressnet) | XpressNet |
| Digitrax | Any      | [MRBW-WIFI](#esu-cabcontrol-jmri-wifi-throttle-and-digitrax-lnwi) - also requires [LNWI](http://www.digitrax.com/products/wireless/lnwi/) module* | LNWI |
| MRC   | Prodigy     | [MRBW-WIFI](#esu-cabcontrol-jmri-wifi-throttle-and-digitrax-lnwi) - also requires [Prodigy WiFi](https://www.modelrectifier.com/Prodigy-WiFi-s/332.htm) module* | WiThrottle |
| CVP   | EasyDCC     | [MRBW-WIFI](#esu-cabcontrol-jmri-wifi-throttle-and-digitrax-lnwi) with JMRI (Example from [The Hills Line](https://thehillsline.com/2020/03/05/fahrvergnugen/)) | WiThrottle |
| Other |             | If it's compatible with JMRI, you can interface to it by running JMRI (requires computer running JMRI and appropriate interface to your DCC system) and connecting via the [MRBW-WIFI](#esu-cabcontrol-jmri-wifi-throttle-and-digitrax-lnwi) interface.  JMRI hardware support can be checked [here](http://jmri.sourceforge.net/help/en/html/hardware/index.shtml). | WiThrottle |

*Note: If you already have a working JMRI installation with WiThrottle server, then the LMWI (Digitrax) or Prodigy WiFi (MRC) module is not required.  In that case, connect the MRBW-WIFI to the WiThrottle server using the same settings you would use to connect a cell phone throttle.

!!! question "Why not JMRI WiFi Throttle?"
    Many people have wondered over the years, why doesn't the ProtoThrottle
    speak the JMRI WiFi Throttle protocol directly?  That's a fair question
    and the answer can be quite involved, but it basically comes down to
    reliability and user experience.  The radio protocol used by the
    ProtoThrottle is a highly robust, resilient system designed for reliable
    communication in adverse conditions.  That, combined with the desire for
    plug-and-play operation of the ProtoThrottle in as many use cases as
    possible, drove the initial design decisions to use a receiver as the
    intermediary.

## NCE Cab Bus and Lenz XpressNet

Product Page: [MRBW-CABBUS](https://www.iascaled.com/store/MRBW-CABBUS)

### Setup

### Troubleshooting

## ESU CabControl, JMRI WiFi Throttle, and Digitrax LNWI

Product Page: [MRBW-WIFI](https://www.iascaled.com/store/MRBW-WIFI)

### Setup

### Troubleshooting

## Why not 