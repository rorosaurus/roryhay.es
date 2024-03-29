---
layout: post
title: My overengineered music festival totem
date: 2019-10-09 13:32:20 +0300
description: I used an ESP32 to drive HUB75 LED panels with cute Pokemon animations! # Add post description (optional)
img: blog/furret-totem/demo.gif # Add image post (optional)
fig-caption: He walk! # Add figcaption (optional)
github-repo: https://github.com/rorosaurus/FurretTotem # Add github repo (optional)
tags: [Hardware, PCB, Soldering, ESP, LEDs, Music, Totem]
---

## Wait but how?
* The LED panels are driven by an ESP32, controlled by a phone via Wifi!
* Yes, he's built using "Arduino"! No, they aren't normal "Neopixel" LEDs, they're HUB75!  Yes, he is adorable!
* The LED panels were $25 each and the microcontroller was $5. It's powered by a normal USB battery pack!
* The original pixel art animation was done by the extremely talented [Alex Illustration](https://www.artstation.com/alexillustration)! We used Photoshop to modify the original animation and to make all the other animations!

## Where is Furret?
Furret uses [Meshtastic](https://meshtastic.org/), a peer-to-peer LoRa mesh network, for long range (up to 10km!) reliable texting and GPS coordinate sharing! After getting your hardware (~$30) and setting up the device, join his channel and you can find Furret easily at festivals! We'll try to announce future planned events on Instagram!

[Click here to join his channel](https://www.meshtastic.org/d/#CjAYAyIgmvE-KciSpfpBhmnGTf2xxqEcX0OudQ_G3KwMii1EzjIqClJhdmVGdXJyZXQ), or scan the QR code below!

{% include image.html 
    file="/assets/img/blog/furret-totem/meshtastic-screenshot.png"
    fig-caption="Furret's Meshtastic Channel"
    url="https://www.meshtastic.org/d/#CjAYAyIgmvE-KciSpfpBhmnGTf2xxqEcX0OudQ_G3KwMii1EzjIqClJhdmVGdXJyZXQ"
    alt="Click here to join his channel"
%}

## Special Thanks
* [@alex_illustrat](https://twitter.com/alex_illustrat) - who [originally created the 8bit pixel art for Furret Walking](https://www.youtube.com/watch?v=ylnLUMmBNKc). See more of his work on [ArtStation](https://alexillustration.artstation.com/)!
* [narpy](https://www.youtube.com/channel/UCKYFHftFxQOJghmrEaK32sg) - for [starting the most adorable, wholesome, meme](https://www.youtube.com/watch?v=JVHybsJbTFY)
* [@pikachutotem](https://www.instagram.com/pikachutotem/) - who inspired me to make Furret!
* Sprite_tm, Craig A. Lindley, Louis Beaudoin, and Marc Merlin - for the below libraries and helpful forum posts :)
* [bigclive](https://www.youtube.com/channel/UCtM5z2gkrGRuWd0JQMx76qA) for showing me the [perfect bubble blowing mechanism](https://www.youtube.com/watch?v=BvQtl3ciGcA)!

{% include image.html 
    file="/assets/img/blog/furret-totem/head-bob-loop.gif"
    fig-caption="Thanks for everyone's help!"
    url="https://ravefurret.com"
    alt="link to ravefurret.com"
%}

## Code
This repository isn't meant to be a good sample project, it's just my personal project. It was built on top of so many incredible libraries:
* [Arduino core for the ESP32](https://github.com/espressif/arduino-esp32)
* [SmartMatrix Library for ESP32](https://github.com/pixelmatix/SmartMatrix/tree/teensylc)
  * I did a [dirty hack](https://github.com/rorosaurus/SmartMatrix/commit/c46fe8d7be686caaaa3b7198bc4b7b24c6114df8) to free up some DMA memory to enable Wifi for this project.
* [Animated GIFs on ESP32](https://github.com/marcmerlin/AnimatedGIFs)
* [Arduino plugin for uploading files to ESP32 file system](https://github.com/me-no-dev/arduino-esp32fs-plugin)

## Hardware
* [PCB I designed](https://github.com/rorosaurus/esp32-hub75-driver) to drive HUB75 panels with an ESP32: [Buy on Tindie!](https://www.tindie.com/products/18357/)
  * This part is optional, but *greatly* simplifies your wiring!
* ESP32-DEVKIT-V1: [Amazon ($14 for 2)](https://smile.amazon.com/gp/product/B07Q576VWZ/)
  * You can use a different ESP32 if you don't use my PCB. Just remember to verify it has the required pins mentioned below!
* 128x64px, P2.5, 1/32, HUB75E purchased on [AliExpress](https://www.aliexpress.com/item/32972741517.html?spm=a2g0s.12269583.0.0.48e74198VArDtK)
* Bubble machine extracted from children's bubble wand toy, purchased on [eBay](https://www.ebay.com/itm/332880742452)
* Some PVC pipe and a tripod!
* Furret's powered by a 100Wh USB battery bank! At full brightness, one panel can pull about 2 Amps @ 5 Volts. Since the LED panel power requirements can spike depending on the animation, I recommend running the ESP32 from a separate 5V power source to avoid brownouts due to voltage sag.