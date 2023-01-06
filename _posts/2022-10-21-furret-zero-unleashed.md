---
layout: post
title: Furret Zero Unleashed
date: 2022-10-21 13:32:20 +0300
description: Custom flipper firmware that adds Furret animations! # Add post description (optional)
img: blog/furret-zero-unleashed/qflip.gif # Add image post (optional)
fig-caption: he hack! (..the world!)  # Add figcaption (optional)
tags: [Furret, Flipper, NFC, RFID, Security]
---

I created a custom [Flipper Zero](https://flipperzero.one/) firmware, forked from [DarkFlippers/unleashed-firmware](https://github.com/DarkFlippers/unleashed-firmware), which adds some custom animations and QoL fixes to the already endless potential granted by Unleashed! I'll occasionally update this firmware to keep up with Unleashed releases.

## What's so exciting about this nerdy Tamagotchi?

When a thoughtful friend gifted me a Flipper, I was surprised and excited! Sometimes your friends know you better than you know yourself! 😅 This tool is something I've always wanted to build myself (with a lesser scope), so it's been thrilling to dive in and learn all about these security technologies and how they work. (And how often companies penny-pinch at the cost of physical security.) And that's before you get to the [BadUSB/RubberDucky](https://docs.flipperzero.one/bad-usb) and [GPIO expansion boards](https://docs.flipperzero.one/gpio-and-modules) potential for digital attacks!

For example, when Alesha needed a friend to watch her cat, her apartment complex issued her a spare card key. Using my Flipper, I compared that key with her original to find that they issued a new identifier for this spare! Good security! Now if the spare is lost or copied, that identifier can be marked as untrusted without impacting Alesha's main key. It's a small detail but one that definitely builds confidence in where you live!

{% include video.html 
    file="/assets/img/blog/furret-zero-unleashed/RFID-demo.mp4"
    fig-caption="Demonstrating RFID emulation of previously read RFID!"
    max-width="90%"
    max-height="1000px"
    video-attributes="muted controls autoplay loop"
%}

## "But like, why make this custom firmware?"

When I realized that the Flipper LCD was 128x64px (the same resolution I chose for my [Furret Totem](https://github.com/rorosaurus/FurretTotem) project) I knew what had to be done! It wasn't very tricky to re-render my .gif files into dithered monochrome, separate the frames, and compile them for Flipper. Now others can enjoy these animations too!

{% include image.html 
    url="https://github.com/rorosaurus/furret-zero-unleashed"
    max-width="70%"
    file="/assets/img/blog/furret-zero-unleashed/he-hack.gif"
    alt="Try the firmware to see the other animations!"
    fig-caption="Try the firmware to see the other animations!"
%}

## What's included

* Removed the SD card icon and top bar from the desktop (more room for animations!)
* Added 7 custom Furret animations to shuffle into the idle animation pool
* Imported (and tweaked) [custom Pokemon frames](https://github.com/rorosaurus/furret-zero-unleashed/commit/a29b4cecd711cc64992431160c28a52aca07e448) for iButton, Sub-GHz, RFID, NFC, and updates

## How to install

[Easy Web Updater](https://lab.flipper.net/?url=https://roryhay.es/assets/files/furret-zero-unleashed/furret-zero-unleashed-023.tgz&channel=release-cfw&version=furret-unleashed-023)

[Manual Install Instructions](https://github.com/rorosaurus/furret-zero-unleashed/blob/dev/documentation/HowToInstall.md)

## Happy hacking! Let me know what you think!