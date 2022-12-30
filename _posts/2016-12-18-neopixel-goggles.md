---
layout: post
title: Make your own Neopixel Goggles!
date: 2016-12-18 13:32:20 +0300
description: Learn how to make your own LED goggles and join our squad! # Add post description (optional)
img: /blog/neopixel-goggles.gif # Add image post (optional)
fig-caption: 😵 Feeling dizzy yet? 😵 # Add figcaption (optional)
tags: [Programming, Arduino, Mesh, LEDs, Maker]
---

> ***August 2019 Update***: This project is in its second iteration! Check out the [mesh-network Goggle Squad, powered by the ESP8266](https://github.com/rorosaurus/esp8266-goggles)!

A few months ago I made some custom LED goggles to light myself up at Burning Man 2016!  Since then I found they also fit in well at concerts and festivals I attend.  Since I keep getting questions about how to make them, I decided to throw together a post with some links and tips!

## Build overview

* Time investment: 3-8 hours
* Skills required: soldering, programming
* Cost: ~$40-60

The time investment is really dependent on your proficiency at the required skills and your tendency to be perfectionist with the wiring. :)
Most of the parts I used are available in [a single kit from Adafruit](https://www.adafruit.com/products/2221)!  The main modifications I made on top of this kit are:

* Added a [3 x AAA Battery Holder](https://www.adafruit.com/products/727) to the strap for extended battery life and easy on/off
* Added two [push buttons](https://smile.amazon.com/Gikfun-12x12x7-3-Tactile-Momentary-Arduino/dp/B01E38OS7K/) which wire into PINs on the Trinket to control effects/settings

## How to make your own
You should start by following [this tutorial on Adafruit](https://learn.adafruit.com/kaleidoscope-eyes-neopixel-led-goggles-trinket-gemma).  It's very detailed and gets us most of the way there!

You'll also need to complete the [Introducing Trinket](https://learn.adafruit.com/introducing-trinket) and [All About Arduino Libraries](https://learn.adafruit.com/adafruit-all-about-arduino-libraries-install-use) tutorials.  It's mostly just installing pre-requisites to program the Trinket and use the NeoPixel library.

My custom code for my goggles is available [on my GitHub](https://github.com/rorosaurus/neopixel-goggles).  It's not perfect (I suspect there are a few things I can do to save more bytes and add more effects) but it's good enough for now!  Some effects are borrowed from NeoPixel demos/examples and other open-source implementations, but a few are my own creation!

## Tips and recommendations

* Decide where the wires will go first.  Solder only what's needed for each stage.  Only cut wires to the proper length when there's no other way forward.  Measure twice.
* Line up the LED rings so they start at the same place on each eye.  This simplifies some animation math and code.
* Remove the tinted lenses.  They make it far too difficult to see in dimly lighted environments.
* Just accept that there's going to be light bleed.  (I probably spent 4 or 5 hours trying to engineer several solutions, but failed.)
* Along that vein of thought, like Adafruit continually warns, this is probably not good for your eyes.
* The googles are a little uncomfortable resting on your nose for extended periods.  Add some soft padding.
* If you want to add diffraction lenses, [GloFX sells the same goggles](https://glofx.com/diffraction-kaleidoscope-glasses/goggles/), but you can customize the lenses.  These goggles also usually come with a rubber padding around the rim, which solves the above padding issue, too!
* Especially if you're sharing your goggles, the battery pack wire experiences a lot of stress.  If you don't unplug the battery pack, it might be a good idea to directly solder the + and - wires directly to the Trinket to avoid it getting unplugged often.  Reinforce your solder joints with hot glue.  Reinforce the wiring at the base of the battery pack with hot glue.  Reinforce the battery wires at a few points in-between with hot glue.
* I usually fix the battery pack to the goggle strap with some electrical tape.

That should be plenty of info for you to get started!  Email me if you have any questions!
