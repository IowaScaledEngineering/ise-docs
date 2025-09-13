---
title: User Manual
---
# SoundBytes Custom User Manual

## Overview

The SoundBytes Custom is a programmable sound player that plays sounds from
a microSD card in response to various trigger events.  Up to four triggers
can come from sensors, switches, detectors, Arduinos, etc. and each trigger
can play a different sound.  It supports various playback modes ranging from
ambient background sounds, triggered sound effects, and a special
beginning-middle-end mode for repeating effects with lead-in and lead-out
sound clips.

Complete with control board, speaker, and microSD card, the SoundBytes
Custom is a turney solution for adding sound to your model railroad, module,
diarama, or other display.

### Features

* Custom sounds loaded using a microSD card
* Four independent triggers with individual sounds
* Features four playback modes: ambient, one-shot, continuous, and beginning-middle-end
* Triggerable by a switch, pushbutton, Arduino, or any other [open-collector](http://localhost:8000/Tips%20and%20Tricks/Articles/opencollector/) output
* Compatible with [TrainSpotter](https://www.iascaled.com/trainspotter) and [ATOM](https://www.iascaled.com/atom) detectors
* Comes complete with speaker, control board, and microSD card
* Powered from 5V to 24V DC

### Typical Applications

* Ambient background sound:  
  Examples: nature sounds, farm animals, traffic
* Triggered sound effects:  
  Examples: FIXME...

---

## Quick Start Guide

### Step 1 - Power

The Soundbytes Custom can be powered from 5V to 24V DC, applied through connector J1
(positive to VIN, negative to GND).  Alternatively, the mini USB jack can be
used to power the Squealer, either from a USB charging block or a laptop/PC.

[FIXME: power image]

### Step 2 - Speaker

The speaker attaches to connector J6 (SPK OUT) on the board.  The plastic
speaker enclosure can be mounted above or below the layout.  For better
sound fidelity, bore a 3/8" hole in the scenery or benchwork, and position
the speaker enclosure with the opening on the side facing up.  Camouflage
the hole with scenery.  However, this is user preference and may involve
some experimentation.

[FIXME: speaker connection]

### Step 3 - Trigger Input(s)

FIXME... talk in general about what the triggers look like (switch to GND). 
Show where to connect.  Switches, pushbuttons, TrainSpotter, ATOM.  Can also
come from Arduino or other electronic module, but must be an open collector
(link) output.  Warning: Do not apply more than 3.3V to the INx inputs.

### Step 4 - Sound File(s)

FIXME... Add sound files can be added to microSD card.  Must meet specific
formats and be in specific locations on the card.  See [section] below for
details.

---

## Operation

After powering up, the blue LED will blink four times to indicate the
SoundBytes Custom is ready.  If no microSD card in inserted, or no valid
sound files are found on the card, the blue and orange LEDs will blink
alternately.

### Volume Control

The volume has 30 levels and comes preset at level 20.  Level 0 is mute. 
There are ten levels above 20 to amplify custom audio tracks with low gain,
but these levels should be used with caution as they may cause distortion.

To change volume, press the VOL UP or VOL DN button.  The amber LED will
blink briefly in response to pressing the button.  When setting volume level
20, the amber LED will blink somewhat longer than normal to indicate it is
the default level.

### Sound Files

Sounds can be loaded using a microSD card.  The sound files need to be put
in folders, with specific folder names, on the microSD card.  See the 
[Modes of Operation](#modes-of-operation) section for details.

The microSD card must be formatted as FAT and the sounds must also meet the following requirements:

* WAV file named with .wav extension (e.g. mp3 or other formats will not work)
* Place .wav file(s) in the main directory of the microSD card (all other sub-directories and their contents are ignored)
* 16-bit, mono format
* 8, 16, 32, or 44.1kHz sample rate

### Option Files

For some modes of operation, additional files (option files) are required to
be present on the microSD card to select the mode and/or configure the
behavior of the sound player.  These option files must have specific - and
exact - filenames.  The contents of the files, however, does not matter -
they can be empty.  Details of the specific option files needed can be found
in the [Modes of Operation](#modes-of-operation) section.

!!! warning "Filename Extensions"
    Windows defaults to hiding filename extensions when viewing files on the
    microSD card.  The ".opt" extension in the option filename must be
    present and cannot not be followed by any other characters.  The best way to
    verify this is by turning off the hiding of filename extensions in
    Windows Explorer: under Options, select the View tab and then uncheck
    the box for "Hide extensions for known file types".

---

## Modes of Operation

### Ambient Mode

In Ambient Mode, the SoundBytes Custom will continuously play the sound
files in random order.  When triggered, by any input, the volume will be
unmuted allowing the sound to play through the speaker.  After the trigger
goes away, the volume will be muted.  Even while muted, the sound files
continue to play internally, even though no sound it emitted by the speaker. 
This provides a level of inherent randomization to the sound once the
module is triggered.

To configure Ambient Mode, a folder named **ambient** should be present in
the root directory of the microSD card.  The sounds in this folder will be
played randomly.

!!! note "Please Note"
    If a folder named **ambient** is found on the microSD card, then Ambient
    Mode will be selected.  This takes precedence over any other mode of
    operation below, regardless of any other folders present on the microSD
    card.

### Triggered Mode

If the device is not in Ambient Mode, then it defaults to triggered mode. 
In triggered mode, the playback of sounds depends upon the state of the four
trigger inputs.  Each trigger input can activate a different set of sounds,
each with different behaviors as detailed below.

For triggered mode, folders named **event1**, **event2**, **event3**, and/or
**event4** should be present on the microSD card.  The specific trigger input
activated determines which folder, and the sounds contained within, which
will be played.  For example, if the IN3 trigger input is activated, then
the sounds from the **event3** folder will be played.

!!! note "Please Note"
    Only one trigger can be active at the same time and only the sound(s)
    for the first trigger will play.

#### One-Shot Mode

In One-Shot Mode, a randomly selected sound file from the event folder will
be played.  Playback will end when the sound file completes playing,
regardless of the state of the trigger input.  Playback will not repeat
automatically, but can be retriggered by first releasing the trigger input
and then re-activating it.

##### Option Files

| Option File     | Description |
| --------------- | ----------- |
| (none)          | No option files should be present for One-Shot Mode |

#### Continuous Mode

When initially triggered, Continuous Mode will randomly play a sound file
from the event folder.  After finished playing, if the trigger is still
active, then either the same - or a newly selected - sound file will be played. 
This repeats indefinitely while the trigger input is active.

##### Option Files

| Option File     | Description |
| --------------- | ----------- |
| continuous.opt  | Must be present to select Continuous Mode. |
| shuffle.opt     | Determines the behavior when a sound file finishes playing and the trigger is still active.  If present, randomly selected files will be played in succession.  If not present, then the first randomly selected file will be repeated in a loop. |
| level.opt       | If present, then playback stops immediately when the trigger is released.  Otherwise, playback continuues through the end of the currently playing sound file. |

#### Beginning-Middle-End Mode

FIXME...

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
