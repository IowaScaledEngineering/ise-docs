---
title: User Manual
---
# ProtoThrottle User Manual ![](img/pt-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}

!!! note warning
    This online ProtoThrottle manual is a work in progress.  For the complete
    manual, please download the PDF version from the [product page](https://www.iascaled.com/store/MRBW-CST).

## Overview

![](img/pt.jpg){align=right}Our goal was to design and develop a wireless throttle that provides the
diesel modeler with the most realistic experience operating their model
locomotives.

The ProtoThrottle mimics a standard EMD control stand including full detent
throttle and reverser handles, a spring-loaded horn handle, a
push-on/push-off bell button, and fully programmable front and rear
headlights with a setting for ditch lights.  In addition, the ProtoThrottle
comes with a robust faceplate machined from aluminum, including prototype
bezels, and anodized to give the look and feel of a real control stand.

The ProtoThrottle comes with our commitment to your satisfaction.  We
warranty the throttle from manufacturing defects for one year, and if you
should have any questions or issues with the ProtoThrottle, please contact
us.

![](img/sigs.png)

---

## Controls

![](img/controls.png)

---

## Battery Install

![](img/battery2.jpg){align=right width=25%}![](img/battery1.jpg){align=right width=25%}The ProtoThrottle is powered by 2 AA batteries (not included).  The
batteries can be alkaline or rechargeable NiMH.

To access the battery holder, unscrew the 4 phillips head screws on the
corners of the throttle’s faceplate; remove the box; **IMPORTANT:** when
removing the batteries from the holder, use one hand to hold both sides of
the holder to prevent it from bending away from the printed circuit board;
insert batteries and reattach the box.  **Do not over tighten the screws.**

**To conserve battery life:** make sure the throttle handle is in “idle”
position and the reverser handle is in “centered” position when not in use. 
This will cause the throttle to go to sleep after 5 minutes.  **To power down
manually, see the [Main Screen](#main-screen) instructions.**

---

## Quick Start Guide

!!! note inline end
    **If the ProtoThrottle is in ”sleep” mode the LCD screen will be dark,
    click any of the LCD buttons to wake the throttle.**

The ProtoThrottle will work with any scale and with sound- or non-sound
decoders (though using sound enhances the control stand experience signifi-
cantly).  Any DCC decoder compatible with the NMRA standards will work with
the ProtoThrottle because it uses standard DCC commands and functions via
your command station..  The ProtoThrottle is not a DCC system and will not
replace the system you use.

Check the Iowa Scaled Engineering
[website](https://www.iascaled.com/store/Receivers) for the most current list of
supported DCC command stations.

!!! success "Step 1"

    Configure your ProtoThrottle receiver using the instructions provided
    with the receiver.  Make sure the base address of the ProtoThrottle matches
    that of the receiver.  If using multiple ProtoThrottles, set
    each throttle to a unique ID.  (See [Communication Configuration Menu](#communication-configuration-menu))

!!! success "Step 2"

    Using your DCC system, **set acceleration momentum (CV3) mid-range to
    moderately high** so that the ProtoThrottle will need to “notch up” to get the
    train moving.

    **Set deceleration momentum (CV4) high or maximum.**  This will allow the train
    to “coast” when the throttle is in the idle position requiring the use of
    the brake to slow or stop the train.

!!! success "Step 3"
    **Input the locomotive number into the ProtoThrottle:**

    1.  Click the Menu button 5 times

        <pre class="lcd screen">
             SET
        &#257;-  LOCO
        </pre>

    1.  Click the Select button once

        <pre class="lcd screen">
          0003&#254;&#254;
          ^
        </pre>

    1.  Use the Up and Down buttons to change numbers

        <pre class="lcd screen">
          4003&#254;&#254;
          ^
        </pre>

    1.  Use the Menu button to move cursor right

        <pre class="lcd screen">
          4003&#254;&#254;
           ^
        </pre>

    1.  Repeat to enter the rest of the numbers

        <pre class="lcd screen">
          4795&#254;&#254;
             ^
        </pre>

    1.  After number is input, click Select button to save

        <pre class="lcd screen">
         SAVED!&#254;
        &#254;
        </pre>

    See [Set Locomotive Menu](#set-locomotive-cenu) for how to set a short (primary) address. 

**NOTE: the ProtoThrottle function settings are set to standard DCC function numbers by default.
If you need to change any function number, the steps are explained below:**

!!! success "Step 4"
    **To check or set the horn, bell, and brake function numbers:**

    1.  Click the Menu button 7 times

        <pre class="lcd screen">
          CONFIG
        &#257;-  FUNC
        </pre>

    1.  Click the Select button once

        <pre class="lcd screen">
        HORN&#254;&#254;&#254;&#254;
        F02
        </pre>

    1.  Click the Up or Down button to change the function number

        <pre class="lcd screen">
        HORN&#254;&#254;&#254;&#254;
        F07
        </pre>

    1.  Click Menu button to toggle through the other function choices. Repeat to change additional functions.

        <pre class="lcd screen">
        BRAKE&#254;&#254;&#254;
        F10
        </pre>

    1.  Click the Select button to save all changes

        <pre class="lcd screen">
         SAVED!&#254;
        &#254;
        </pre>


!!! success "Step 5"
    **Enjoy operating your locomotive!**

    **Please read the entire manual to familiarize yourself with all the
    features of the ProtoThrottle.** See our website for more specific
    instructions on programming.

    In addition, our website has detailed operational scenarios developed by
    professional locomotive engineer, Tim Garland.  If you are not familiar
    with prototype operation from a engineer’s perspective, Tim’s scenarios
    will give you insight on how to operate more realistically using the
    ProtoThrottle.

---

## Main Screen

!!! info ""
    <pre class="lcd screen">
    <font class="faint">&#265; </font>0250<font class="faint"> &#268;</font>
    <font class="faint">&#274;12:00&#270;&#268;</font>
    </pre>

    Locomotive Address.  Long (extended) addresses are displayed directly (e.g. 0250 0000 9999). Short (primary) addresses are displayed with an ‘s’ prefix (e.g. <span class="lcd">s003 s000 s127</span>).

    In certain situations the locomotive address may be replaced by an alert message:

    <span class="lcd">EMRG </span> Emergency stop is active!
    Note: move the brake handle all the way left to deactivate.

    <span class="lcd">REV! </span> Reverser was moved with the throttle not in idle|

!!! info ""
    <pre class="lcd screen">
    <font class="faint">&#265; 0250 &#268;</font>
    <font class="faint">&#274;</font>12:00&#270;<font class="faint">&#268;</font>
    </pre>

    The ProtoThrottle acts as a secondary display for Iowa Scaled
    Engineering’s wireless fast clocks www.iascaled.com/store/MRBW-FCM
    or the fast time provided by the NCE Cab Bus.

    <span class="lcd">&#174;</span> 12-hour mode AM indicator<span class="lcd"> &#175;</span> 12-hour mode PM indicator

    No AM or PM indicator when in 24-hour mode.

!!! info ""
    <pre class="lcd screen">
    &#265;<font class="faint"> 0250 &#268;</font>
    <font class="faint">&#274;12:00&#270;&#268;</font>
    </pre>

    Battery Status:
    
    <span class="lcd">&#265; </span>Batteries good

    <span class="lcd">&#266; </span>Batteries low

    <span class="lcd">&#267; </span>Replace batteries
    
    Display will show<span class="lcd"> LOW BATTERY </span>when the batteries are critically low. Operation will not be possible
    until the batteries are replaced.

!!! info ""
    <pre class="lcd screen">
    <font class="faint">&#265; 0250 &#268;</font>
    &#274;<font class="faint">12:00&#270;&#268;</font>
    </pre>
    When<span class="lcd"> &#274; </span>is on screen the auxiliary button is active

!!! info ""
    <pre class="lcd screen">
    <font class="faint">&#265; 0250 </font>&#268;
    <font class="faint">&#274;12:00&#270;</font>&#268;
    </pre>

    Up/Down Button Status.  On the main screen, the Up and Down buttons can
    be assigned to functions.  The on/off status of those assigned functions
    are displayed on the LCD screen.

    <span class="lcd">&#268; </span>Function off

    <span class="lcd">&#269; </span>Function on

**Note:** pressing and holding the Menu button (upper left LCD button)
momentarily will return you to the main screen from any of the main
menus.

|     | Navigation |     |
|----:|:----------:|:----|
|Advance to Engine Menu :material-arrow-right-drop-circle:<br><br>Toggle backlight on/off :material-checkbox-marked-circle:<br>**hold** to power down throttle|<br>LCD SCREEN<br> |:material-arrow-up-circle: Up<br><br>:material-arrow-down-circle: Down|

The Up and Down buttons can be assigned a function using the [Configure Function](#configure-function-menu) menu.

Pressing and holding the Select button for a few seconds will prompt to power down the throttle:

<pre class="lcd screen">
POWER
DOWN  -&#256
</pre>

Click the Down button to confirm and turn off the throttle.
