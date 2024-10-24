---
title: Introduction to MSS
---
# Introduction to MSS ![](../img/simplesig-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}

## What is the Modular Signal System?

The Modular Signal System (MSS) is a way to bring an approximation of a basic North American Automatic Block Signal system to a model railroad that is both easy to understand and easy to implement.  There are no computers involved whatsoever in the basic setup.  The simplest version is just a matter of installing signal and signal modules, detectors, and then linking the whole thing together with standard "crossover" type ethernet cables.

MSS was designed to be incredibly simple to set up and robust because of its roots in the FreeMo modular community  The initial standard was put forth by Gregg Fuhriman back around 2004, and it first got widespread exposure in the Feburary 2005 issue of Railmodel Journal.  What Gregg and team have developed is nothing short of brilliant in its elegant simplicity.  Being able to just plug one signaled module into the next and have them "just work" was key to success.

MSS is not going to model your prototype’s strangest interlockings and aspect rules straight out of the box, though realistically with a bit of custom work you can likely get close.

It's a completely open standard, and


## How is SimpleSig Different from MSS?

SimpleSig is just simply Iowa Scaled Engineering's line of signaling products for model railroads.  Most of the SimpleSig products are intended to be robust, easy to use, MSS-compatible components, though we do have a few accessories and stand-alone signal products that will be added to the line as well.

## What Prototype Does MSS Model?

The basic MSS standard is close to ABS, or automatic block signaling.  

There's no reason that MSS cannot be extended to more accurately represent more complicated signal regimes as well.  

## MSS Terminology

Honestly, the worst part of MSS is the terminology.  It's somewhat confusing, but once you get the general terms down it starts to make sense.

### Crossovers

MSS depends upon "crossovers" so that the outputs of one signal module get wired to the correct pins on the next.  The "Golden Rule of MSS" is that you absolutely must have an odd number of crossovers between signal modules (cascades).

This can be as simple as a single "crossover" network cable, where rather than going straight through, pins 1 & 2 get swapped, as do pins 3 & 6.  However, the word "crossover" however often refers to what we at ISE refer to as a [/Modular Signal System/Crossover Detector/manual/](Crossover Detector).  These are devices which do cross over the signal wires, but also provide a DCC block detector.  They're often used on modules without actual signals, but that do have proper block detection so they can participate in signaled FreeMo setups.

Crossover Detectors are very important in FreeMo and FreeMoN setups, but are not particularly useful for home layouts where the user can install a single block detector to cover the entire block, rather than needing one on each layout module.

### Cascades



### Complex Cascades

Complex Cascades build on regular Cascades.  Whereas normal cascades just provide two signals at a block boundary and rearrange some signals, Complex Cascades model complex trackwork and route the various MSS signals to follow whatever routes are connected.  The end of a siding is an excellent example.  

When the turnout is lined for the main, you want the MSS bus from the point end of the turnout connected to the MSS bus following the main track.  You also want to make sure the signal at the end of the siding is displaying stop since the turnout is set against it, and then send the appropriate signals down the siding MSS bus to indicate to display approach, advance approach, etc.  

If the turnout is lined to the siding, you want the opposite behavior.  You want the MSS bus from the points connected to the MSS bus from the siding, and you want the main signal to display stop and trickle that back up the maine line MSS bus.


---

## Open Source 

Iowa Scaled Engineering is committed to creating open designs that users are free to build, modify, adapt, improve, and share with others.  Nearly all of our products are open hardware and open source software.  Design files can be found on our [GitHub account](https://github.com/IowaScaledEngineering/).
