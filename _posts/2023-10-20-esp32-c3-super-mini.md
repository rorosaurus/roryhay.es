---
layout: post
title: Cheap (W)LED controller - ESP32-C3 Super Mini
date: 2023-10-20 13:32:20 +0300
description:  My new favorite cheap (W)LED controller! # Add post description (optional)
img: blog/esp32-c3-super-mini/esp32-c3-super-mini.jpg # Add image post (optional)
fig-caption: Tiny but powerful!  # Add figcaption (optional)
github-repo: # Add github repo (optional)
tags: [Maker, Soldering, LEDs, ESP32, WLED]
---

I'm always on the lookout for a new favorite microcontroller. The ESP family has been my favorite for quite some time now, and the new C3 chip offers quite a lot in a super cheap package! I assume that's due to its RISC-V architecture reducing licensing costs for Espressif.

## What's it got?
This tiny board can be had for less than $2.50 and comes in at 18mm x 22.5mm - perfect for tiny projects! The C3 only has a single CPU core @ 160MHz, which is a downgrade from the 240MHz dual core LX6 CPU on the original ESP32. Connectivity-wise, the C3 still has 2.4 GHz Wi-Fi (802.11b/g/n) and Bluetooth® 5 (LE). This Super Mini dev board uses the optional 4 MB flash integrated in the C3's tiny QFN32 (5×5 mm) package.

## Why's it good for WLED?
The USB-C connector and PCB traces are robust enough to handle 5V@3A continuously from my testing, so it's an ideal little WLED driver for some small 5V LED projects. As usual, you can get away without a level shifter if your data line is short enough (less than a couple feet). The antenna component has better range than PCB trace antennas too! My biggest concern was that Wifi communication would freeze LED animations for a brief moment, which certainly does happen sometimes - but not always, and only when you're changing things. In my experience, this was not nearly as big of a deal as I worried it might be.

The C3 still has one I2S port, which I was able to confirm works with WLED Audioreactive, or u/Yves-Bazin's [24-way parallel driver for FastLED](https://www.reddit.com/r/FastLED/comments/bjq0sm/new_24way_parallel_driver_for_esp32/). The Super Mini doesn't break out 24 GPIO, but it's pretty cool that you can drive 11 different LED strips directly from this dev board! Note that WLED uses NeoPixelBus though, so you're currently [limited to 2 parallel strips on WLED](https://kno.wled.ge/features/multi-strip/).

The BOOT pushbutton is wired to GPIO9, which you can program in WLED to a simple ON/OFF or change animation button. If you're having trouble flashing firmware, hold the BOOT button before plugging in your USB and make sure you're using a cable that supports data!

The best part? The C3 has a USB/Serial interface built-in! No extra IC on the dev board increasing the footprint size or cost! Just plug in your Super Mini, navigate to https://install.wled.me, and install WLED on your board in less than 2 minutes! Then it's just a matter of soldering a few wires to your LED strip!

## What's lacking
* No battery power option or management
* No on/off switch
* No 2nd CPU core means heavy Wifi bursts can interfere with animations

In my opinion these are relatively minor tradeoffs for many of my projects, making the Super Mini my new favorite cheap microcontroller! Soon I might even design my own dev board to address the battery power drawback - stay tuned!

## Links

* [Super Mini Pinout](https://www.nologo.tech/product/esp32/esp32C3SuperMini.html)
* [AliExpress](https://www.aliexpress.us/item/3256805910402296.html)