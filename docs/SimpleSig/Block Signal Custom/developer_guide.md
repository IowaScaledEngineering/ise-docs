---
title: Developer's Guide
---
# Block Signal Custom Developer's Guide ![](../img/simplesig-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}

## Overview

The Iowa Scaled Engineering [Block Signal Pro](https://www.iascaled.com/store/MSS-XCADE) an insane, fever dream that nobody will ever buy or understand.

## Developer's Guide

The Block Signal Custom is designed to solve all manner of complicated signaling problems with MSS that could never be a dedicated product.  It provides a generic set of building blocks - MSS ports, signal drivers, sensor inputs, and general purpose input/output (GPIO) - that can be developed into a signal solution for even the strangest trackwork.

While we intend to ship a version of it with factory firmware that solves a variety of common situations (diamonds, double track crossovers of various types, etc.), this will be far from everything.  This guide is meant to help someone with some amount of programming skills develop their own custom solutions for the board.

In order to make programming the board as (relatively) friendly and painless as possible, the system is programmed through the Arduino environment, and a library is provided to abstract off a lot of the detail and allow the user to focus on the signal logic itself.

## Getting Started - Environment Setup

### Set Up the Arduino Environment

For this, you'll want to install the latest release of version 2 of the Arduino IDE.  You can download the correct version for your computer's OS from [the official Arduino.cc site](https://docs.arduino.cc/software/ide/).

Once installed, open up the board manager (Shift+Ctrl+B or Tools->Board->Board Manager) and search for "esp32".  Install "esp32 by Espressif Systems"

Once you get the esp32 board support installed, you'll want to select the correct settings in the Tools menu.

* In Tools->Board, select "esp32" and then "ESP32S2 Dev Module".
* Plug in the MSS-XCADE and select the right serial port for it under Tools->Port.
* Once you've done that, a bunch of new options for the ESP32s should appear below.  Set those as follows:
** Tools->USB CDC on Boot should be Enabled
** Tools->PSRAM should be Enabled
** Tools->Erase All Flash Before Sketch Upload - I often set this to enable because it can clear out some weird bugs, but not strictly needed
* Open up Preferences (File->Preferences)  and change "Compiler Warnings" to "Default".   Trust me, warnings are a good thing, particularly with ESP32s.  Because the serial console is done through the USB stack, if the processor goes off into la-la-land, you will spend hours chasing around why.  Compiler warnings, such as forgetting to return a value from a function that needs a return value, will tell you about these ahead of time and save you much time.
* (Optional) Personally, as someone used to robust syntax highlighting in my code editors, I also can't stand the Arduino default theme.  To fix that, I download the default VSCode syntax highlighting and install it as a customized theme.  [This thread](https://forum.arduino.cc/t/personal-themes/1024606) gives the instructions for that, and I've placed the VSCode default C/C++ v2.0.0 [here](./ms-vscode.cpptools-themes-2.0.0.zip).  If you like it, or you're used to it, more power to you, but I find having good syntax highlighting really helps me see stupid mistakes.

### Install the MSS-XCADE Library

The key to controlling the MSS-XCADE board is the library written around it.  This makes it easy to control without having to know exactly where each wire goes on the board.  You can write software thinking about signal concepts, not about hardware schematics.  It also has some examples with it to show you how various things are done.

I haven't made the MSS-CADE control library accessible through the general Arduino library manager, because it's a very specialized application.  You can easily download the latest 
Download the latest MSS-XCADE library zip file from the IowaScaledEngineering/mss-xcade-lib project. You can get the most recent zip file [from here](https://github.com/IowaScaledEngineering/mss-xcade-lib/archive/refs/heads/master.zip). Use Sketch->Include Library->Add .ZIP Library and select the zip file you just downloaded.

## Hardware Considerations

!!! warning "GPIO Pin Limitations"
    The GPIO lines are 5V logic lines tied into a TCA9555 I/O expander.  Do NOT exceed 5V on these pins or draw more than 20mA, otherwise permanent, irreparable damage to the board may result.


## Basic Concepts

The root of everything is the XCade object.  It represents the features that are available on all MSS-XCADE boards, both the masters with the host ESP32-S2, and any expansion boards.  One XCade object will be used for each board.   Through it, you will interace with the board's basic four resources - eight signal head drivers, four MSS ports, ten sensor inputs, and six 5V-capable general purpose I/O (GPIO) lines.

MSS Ports are accessed as MSSPort objects:
* xcade.mssPortA
* xcade.mssPortB
* xcade.mssPortC
* xcade.mssPortD

Signal heads are accessed through SignalHead objects:
* xcade.signals.A1
* xcade.signals.A2
* xcade.signals.B1
* ..and so on, through D2.

Sensors and GPIO lines work much like the Arduino digital pins - pinMode, digitalRead, and digitalWrite - are both accessed through the gpio interface.  The sensor inputs are naturally inverted, since all ISE sensors that plug into them are open collector, and thus active low.  So went a sensor is triggered, digitalRead() will return true, and when it's not triggered it will return false. The GPIOs are not inverted and reflect the true state of the GPIO line.  All of them are accessed through the GPIO object:
* xcade.gpio

In order to understand all of this, I recommend opening up the "basic-abs" example.  It does little more than provide a simple ABS block boundary, and while that's a massive waste of the xcade's resources, 
it's an ultra-simplified example of how to use the various pieces of hardware on the board and the software library around them.

---

## RGB LED

The main MSS-XCADE has an RGB LED (WS2812B) attached and marked "STATUS".  Developers can use this to give users a visual indication of what the board is doing.  It's attached to GPIO 45 of the ESP32-S2.

It can be exercised using the built-in function in the ESP Arduino wrapper library:

rgbLedWrite(RGB_LED_GPIO, red, green, blue);

RGB_LED_GPIO is defined as 45 in the mss-xcade.h header, and red, green, and blue are values between 0-255.

---

## Interface Expansion Board

The six-pin header just under the ISE logo can be used to connect with various communications networks, such as RS485 or CAN.  In theory, this means that the board should be able to support interfacing with things like CMRI or LCC given the correct adapter board.

Other than testing for basic functionality, no development has been done yet on this possibility.

The pinout is as follows:
* 1 - AUX1, connected to GPIO41 on the ESP32-S2.  Intended to be used for TXEN on RS485 networks or similar
* 2 - Ground
* 3 - TX - Transmit from the ESP32 to the network, connected to GPIO 39 of the ESP32-S2
* 4 - RX - Receive from the network to the ESP32, connected to GPIO 40 of the ESP32-S2
* 5 - Positive power input - Protected by a diode, this is intended to allow buses like LCC that carry power to supply it to the MSS-XCADE's onboard switching regulator
* 6 - +5V supplied by the MSS-XCADE board to the adapter board

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
