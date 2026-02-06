---
title: User Manual
---
# SoundBytes Custom User Manual

!!! note "Please Note"
    This is a future product and subject to change.  Release date is targeted for January 2026 and
    will be officially announced in our email [newsletter](https://www.iascaled.com/store/). 

## Overview

The SoundBytes Custom is a programmable sound player that plays sounds from
a microSD card.  It supports various modes of operation ranging from ambient
background sound, event initiated sound effects, and a special
beginning-middle-end mode for repeating effects with lead-in and lead-out
sound clips.  Up to four events can initiate playback and each event can
cause a different series of sounds to play.  These events can come from
sensors, switches, various detectors, Arduinos, etc.

Complete with control board, speaker, and microSD card, the SoundBytes
Custom is a turnkey solution for adding sound to your model railroad, module,
diarama, or other display.

### Features

* Custom sounds loaded using a microSD card
* Features four playback modes: ambient, one-shot, continuous, and beginning-middle-end
* Four independent events with individual sounds
* Playback can be initiated with switches, push buttons, an Arduino, or any device with an [open-collector](/Tips%20and%20Tricks/Articles/opencollector/) output
* Compatible with [TrainSpotter](https://www.iascaled.com/TrainSpotter) and [ATOM](https://www.iascaled.com/Atom) detectors
* Comes complete with speaker, control board, and microSD card
* Powered from 5V to 24V DC

### Typical Applications

* Ambient background sounds  
* Sound effects  
* Voice narration  

---

## Quick Start Guide

### Step 1 - Power

The SoundBytes Custom is powered from 5V to 24V DC, applied through connector J1
(positive to VIN, negative to GND).  Alternatively, the mini USB jack can be
used to power the SoundBytes Custom, either from a USB charging block or a laptop/PC.  

![](img/snd-player-power.jpg)

To power the SoundBytes Custom directly from the DCC bus, a 
[power adapter](https://www.iascaled.com/store/CKT-DCCPWR) is available.

### Step 2 - Speaker

The speaker attaches to connector J6 (SPK OUT) on the board.  It can be
mounted above or below the layout.  When mounting it below, a hole can be
bored in the scenery or benchwork and covered, for better sound fidelity. 
This may involve some experimentation.

![](img/snd-player-spk.jpg)

### Step 3 - Event Input(s)

Various input sources can be used to initiate sound playback on the
SoundBytes Custom.  In all cases, the input should be connected to GND when
you want sound to play.  This can be done with a switch, a push button, a
[TrainSpotter](https://www.iascaled.com/TrainSpotter) or [ATOM
detector](https://www.iascaled.com/Atom), or many other devices.  An Arduino
or other electronic module can also be used, but the output should be of an
[open-collector](/Tips and Tricks/Articles/opencollector/) style output.

!!! warning "Maximum Voltage"
    Do not apply more than 3.3V to the inputs.  The SoundBytes
    Custom may be damaged by higher voltages.

The SoundBytes Custom has four event inputs.  These are IN1, IN2, IN3, and
IN4 on the terminal blocks around the perimeter of the board.  The G
terminals provide a convenient GND location to which the IN terminals can be
connected via switches, push buttons, etc.

![](img/snd-player-in12.jpg)
![](img/snd-player-in34.jpg)

Additionally, power and GND for powering sensors (like a TrainSpotter or ATOM
detector) can be found on the SNS PWR and SNS GND terminal blocks,
respectively.

### Step 4 - Sound File(s)

Add sound files to the microSD card.  See the [Sound Files](#sound-files)
section below for details.

---

## Operation

After powering up, the blue LED will blink four times to indicate the
SoundBytes Custom is ready.  However, if no microSD card is inserted, or no valid
sound files are found on the card, the blue and orange LEDs will instead blink
alternately.

### Volume Control

The volume has 30 levels and comes preset at level 20.  Level 0 is mute. 
There are ten levels above 20 to amplify custom audio tracks with low gain,
but these levels should be used with caution as they may cause distortion.

To change volume, press the VOL UP or VOL DN button.  The amber LED will
blink briefly in response to pressing the button.  When setting volume level
20, the amber LED will blink longer than normal to indicate it is the
default level.  When at the minimum or maximum volume levels, the amber LED
will blink rapidly.

### Sound Files

Sounds can be loaded using a microSD card.  The sound files need to be put
in folders, with specific folder names, on the microSD card.  See the 
[Modes of Operation](#modes-of-operation) section for details.

The microSD card must be formatted as FAT and the sounds must also meet the following requirements:

* WAV file named with .wav extension (e.g. mp3 or other formats will not work)
* 16-bit, mono format
* 8, 16, 32, or 44.1kHz sample rate

### Option Files

For some modes of operation, additional files (option files) are required to
be present on the microSD card to select the mode and/or configure the
behavior of the sound player.  These option files must have specific, and
exact, filenames.  The contents of the files, however, does not matter -
they can be empty.  Details of the specific option files needed can be found
in the [Modes of Operation](#modes-of-operation) section.

!!! warning "Filename Extensions"
    Windows defaults to hiding filename extensions when viewing files on the
    microSD card.  The ".opt" extension in the option filename must be
    present and cannot be followed by any other characters.  The best way to
    verify this is by turning off the hiding of filename extensions in
    Windows Explorer.  Do this under Options, select the View tab and then uncheck
    the box for "Hide extensions for known file types".

---

## Modes of Operation

### Ambient Mode

In Ambient Mode, the SoundBytes Custom will continuously play the sound
files in a random order.  When any input is connected to GND, the volume will be
unmuted allowing the sound to play through the speaker.  With no inputs
connected to GND, the volume will be muted.  Even while muted, the sound files
continue to play internally, although no sound is emitted by the speaker. 
This provides a level of inherent randomization to the sound each time the
volume is unmuted.

To configure Ambient Mode, a folder named **ambient** should be present in
the root directory of the microSD card.  The sounds in this folder will be
played randomly.

!!! note "Please Note"
    If a folder named **ambient** is found on the microSD card, then Ambient
    Mode will be selected.  This takes precedence over any other mode of
    operation below, regardless if any other folders are present on the
    microSD card.  All four inputs will behave the same in Ambient Mode.

### Event Mode

If the device is not in [Ambient Mode](#ambient-mode), then it defaults to
event mode.  In event mode, the playback of sounds depends upon the state of
the four inputs.  Each input can activate a different set of sounds, each
with different behaviors as detailed below.

In event mode, folders named **event1**, **event2**, **event3**, and/or
**event4** should be present on the microSD card.  The specific input
activated determines the folder, and the sounds contained within, which will
be played.  For example, when the IN3 input is activated, the sounds from
the **event3** folder will be played.

!!! note "Please Note"
    Only one event will be detected and acted upon at any time.  The sound(s) for the first
    event detected will play until that event is complete, followed by any
    other events that are active at that time.

#### One-Shot Mode

In One-Shot Mode, when the input is activated (connected to GND), a randomly
selected sound file from the corresponding event folder will be played. 
Playback will end when the sound file completes playing, regardless of the
state of the input.  Playback will not repeat automatically, but can be
restarted by deactivating the input (disconnecting from GND) and then
reactivating it.

##### Option Files

| Option File     | Description |
| --------------- | ----------- |
| (none)          | No option files should be present for One-Shot Mode |

#### Continuous Mode

When initially activated by connecting the input to GND, Continuous Mode
will randomly play a sound file from the corresponding event folder.  After
playing, if the input is still active (connected to GND), then either the
same sound file will be repeated or a newly selected sound file will be
played (this behavior is determined by the option files below).  Sounds
continue repeating indefinitely while the input is connected to GND.

##### Option Files

| Option File     | Description |
| --------------- | ----------- |
| continuous.opt  | Must be present to select Continuous Mode. |
| shuffle.opt     | (Optional) Determines the behavior when a sound file finishes playing and the input is still active.  If this option file is present, then a randomly selected file will be played next.  If not present, then the first selected file will be repeated in a loop. |
| level.opt       | (Optional) If this option file is present, then playback stops immediately when the input is deactivated.  Otherwise, playback continues through the end of the currently playing sound file. |

#### Beginning-Middle-End Mode

For special use cases, Beginning-Middle-End Mode allows an initial
beginning sound to be played, followed by an indefinite series of middle
sounds, wrapping up with an end sound.  This can be used for things like
whistles or the sound of a train approaching, passing, and leaving.

When the input is first activated (connected to GND), the beginning sound is
played.  If the input is still active at the end of the beginning sounds,
then the middle sound(s) will play in a random order.  Once the input is
deactivated, then the end sound will play.  If the input is not active at
the end of the beginning sound, then the middle sound(s) will be skipped and
the end sound played.

If the sound files all have the same sample rate, then playback in
beginning-middle-end mode is seamless.  This means transitions between the
various sound files happen without any delays.

Specific filenames are required for proper operation.  The beginning and end
sound files must be named exactly as follows:

* begin.wav: the beginning sound
* end.wav: the end sound

Any other files in the folder will be randomly played for the middle
sound(s).

##### Option Files

| Option File     | Description |
| --------------- | ----------- |
| bme.opt         | Must be present to select Beginning-Middle-End Mode. |

---

## Specifications

**Input Power:**  5 to 24 volts DC  
**Size (Control Board):** 3.75"(L) x 2.25"(W) x 0.5"(H)  
**Size (Speaker):** 1.25"(L) x 1.25"(W) x 1"(H)  

---

## Open Source 

Iowa Scaled Engineering is committed to creating open designs that users are free to build, modify,
adapt, improve, and share with others.

The design of the SND-PLAYER hardware is open source hardware, and is made available under the
terms of the [Creative Commons Attribution-Share Alike v3.0 license](http://creativecommons.org/licenses/by-sa/3.0/). 
Design files can be found in the [ckt-soundplay](https://github.com/IowaScaledEngineering/ckt-soundplay) project on 
GitHub.

The firmware for the SND-PLAYER is free software: you can redistribute it and/or modify it under the 
terms of the GNU General Public License as published by the Free Software Foundation, either [version 3 of the 
License](https://www.gnu.org/licenses/gpl.html), or any later version.  Firmware for the snd-player can be 
found in the [snd-player](https://github.com/IowaScaledEngineering/snd-player) project on GitHub.
