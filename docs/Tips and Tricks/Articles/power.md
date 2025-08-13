---
title: Powering Your Layout
---
# Powering Your Layout Electronics


## Overview

One of the most important but least exciting parts of model railroading is having a reliable source of power. It’s like air – nobody notices until it goes bad, or there’s not enough of it.  But as our modeling increasingly integrates more and more electronic components to add realism and enhance the experience, it's a topic we cannot avoid.

There's a reason this is the first "Tips & Tricks" article that I'm posting - a large percentage of our support issues can be traced in some way to power issues.

---

## Don't Use Power Packs

The basic transformer - or "power pack" - has a long and storied history in our hobby.  It’s also a dinosaur, a leftover of an era where there was little more to our layouts than crude electric motors and incandescent bulbs.  The power they produce is ugly, but nothing in their era really cared.  In fact, for controlling motors, dirty ugly power is actually a feature.  That "pulse power" that many throttles offered?  It's a high voltage kick to get the motor to overcome friction.

You know what else that high voltage kick does?  Kills electronics that aren't designed to handle it.

As the hobby has embraced ever more complex electronics, these old terrible power supplies are often damaging to modern electronics.  Even the “DC” output they create is terrible and only DC in the loosest, nastiest sense of the word.

I can't emphasize this enough - power packs are for driving motors and accessories from the 1970s and 1980s.  Please, please, please don't use them for modern electronics.  I don't care if you have the latest, greatest, most expensive new DC power pack from manufacturer XYZ.  The power it puts out is still terrible and really only intended for driving motors, not electronics.

---

## Choosing An Appropriate Supply

Most modern model railroad accessories are going to run best on clean DC power.  Nothing in the electronics world wants AC.  Some will survive AC power and some will even work, because we’re used to customers who don’t really think about power quality and just hook stuff up to whatever.  But it’s because of the terrible power on most layouts that we, as manufacturers, have to include extra and higher rated components on the front end of our products.  That raises the cost of the product and still isn’t enough to assure reliable operation for the worst cases.

There’s two things you want to consider when choosing power supplies – voltage and current capability (amps).  A good DC power supply puts out a steady voltage.  12V is a good choice for model railroad electronics, as it’s usually in that sweet spot where everything will operate.  Because it was the “nominal” voltage that power packs output, and it’s safe for humans to touch without serious electric shock (though you may get a little tingle), it’s become a de facto standard.

Current capacity – or amps – is about how much power the power supply can source.  Most loads are specified to run at a specific voltage (or voltage range) and then will tell you how many amps they will pull from the power supply  Basically, they pull what they need to do the job at the given time.  If you have something that draws 0.2A, another thing that draws 0.1A, and a third thing that pulls 0.4A, you need a power supply that can supply 0.7A (the sum of 0.2 + 0.1 + 0.4) total.

The other thing to think about is that all loads aren’t going to be pulling maximum power all the time.  For example, a twin coil switch machine may pull 1A while it’s throwing, but 0 amps while it’s just sitting there.  If you have 30 switch machines, you don’t need a 30 amp power supply because you’re not going to be throwing all 30 switches at once (probably).  You may only be throwing at most 3-4 switches at the same time, so a 5A supply is probably more than sufficient.  So think about what your average and peak current draw is likely to be when sizing your power supply.

### Option A - Wall Warts

One very cheap option is recycling “wall warts” from electronics you no longer use.   You want to look for units with a DC output of 9-15V.  In this case, strangely, the lighter ones are the better ones.  If a wall wart is heavy, chances are it’s an iron-core transformer inside and usually only a little better than a power pack in terms of power stability.  Light ones are made with modern electronics inside, and provide very efficient, stable, well-regulated outputs.  I always look at the wall warts from electronic gizmos I’m about to toss to see if they’re worth saving for reuse in other applications.  The only downside is that they’re usually limited in current capability – usually only 1-3 amps.  So you may wind up using quite a few of them around the layout.

### Option B - Industrial Supplies

My personal preference is a simple industrial switchmode power supply (SMPS).  Because of the advances in modern electronics, there are very efficient power supplies available that turn 120 or 240VAC wall power into clean DC power at up to tens of amps.  They’re also surprisingly affordable and available.

All you need to make use of them is a power cord connected to the input terminals.  I strongly recommend making sure it's a 3-prong cord, and that ground is properly attached to the power supply.  For safety, the frame of the supply needs to be grounded.  I'd also recommend making sure that they're either unplugged or switched off when the layout isn't in use, and that they're mounted in clear air where nothing is likely to fall in, and away from flammable materials just in case.  Also slapping some electrical tape over the terminal block to reduce accidental contact isn't a bad idea.

Something like a Mean Well LRS-100-12 will supply a clean 12 volts of DC at up to 8.5A from wall power, is 88% efficient, is dead quiet because it doesn't need a fan, and is a whopping $20 from Digikey.  That's enough accessory power for probably 9 out of 10 layouts out there.  For the rest?  Buy a couple and split up the load into districts, the same way you would with DCC boosters and separate power districts.

### Option C - DCC Power

If you're going to be using a number of DCC accessory decoders, a good option is a DCC-based accessory power bus.  This allows you to run your accessories off a separate booster so that even if you short out the track and the trains stop, you can still do things like throw turnouts.

Many modular layouts have adopted this as their standard for distributing accessory power.  Free-Mo and Free-MoN, for example, have a separate accessory DCC bus that's devoted to powering accessories.

Some nice advantages of this option:
* The bus can directly power and control things like switch machine decoders, so if track power gets shorted, you can still throw turnouts
* The booster driving the DCC Accessory Power bus is probably going to come with an appropriately clean, beefy wall power supply
* The booster already has safety features like short circuit protection built in
* DCC is an AC (alternating current) waveform, but since it's a square wave instead of a sine wave, it's easily turned back into clean DC power if that's what's needed.  Our CKT-DCCPWR does just that.

Our CKT-DCCPWR adapter is a great way to turn AC or DCC into clean, filtered DC power.  In addition, many of our newer products and those designed for modular use have the ability to use AC, DC, or DCC power directly.  Check the product features for details.

---

## Safety

!!! warning "A Note On Safety"
    Just because it's low voltage doesn't mean you don't need to think about safety.  12 volts at 20-30 amps can still ruin your day and get the fire department involved in a hurry.  12 volts at 20 amps is 240 watts if it shorts out.  Think about how hot an old incandescent 100 watt light bulb used to get.  Now double it, and that's the sort of energy that could be released in a small area. Good wiring practices, such as properly sizing wire, clean installations, good insulation that prevents accidental shorts, and fusing are important.

Remember to size your accessory power bus wiring for the amount of current it can potentially supply.  I usually use 12-14AWG for the main bus, and 16-18AWG for local connections.

If you do use a power supply capable of sourcing more than 4-5 amps, I’d highly recommend putting in fuses between your main accessory power bus and any smaller wiring.  Automotive blade fuses (ATO / ATC) are available with values of 1-2 amps and are a great choice for branches off the main bus.  There are a number of fuse blocks designed for automotive and boating use that will split a large power supply through fuses into a number of power districts, and these are available from a wide variety of sources including Amazon.






