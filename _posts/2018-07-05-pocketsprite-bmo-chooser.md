---
layout: post
title: BMO Chooser.app for Pocketsprite
date: 2018-07-05 13:32:20 +0300
description: Who wants to play videogaaaames!? # Add post description (optional)
img: blog/bmo-chooser.jpg # Add image post (optional)
fig-caption: Who wants to play videogaaaames!? # Add figcaption (optional)
github-repo: https://github.com/rorosaurus/8bkc-bmo-chooser # Add github repo (optional)
tags: [Programming, ESP, Maker, Gameboy]
---

The first thing you see when you start your [PocketSprite](https://pocketsprite.com/) is the chooser. It's main tasks are to allow you to upload/delete files (including apps) via WiFi Access Point and launch apps that are present on the filesystem.

This is a modified version of the `chooser.app`, which greets you with a smiling [BMO](https://adventuretime.fandom.com/wiki/BMO) face and a short sound clip when you launch it (with wifi disabled).

{% include image.html 
    file="/assets/img/blog/bmo-chooser.jpg"
    fig-caption="Who wants to play videogaaaames!?"
%}

Even with a poor paint job, it's instantly recognizable as BMO!

## Installing
1. Download the [latest version from GitHub](https://github.com/rorosaurus/8bkc-bmo-chooser/releases/latest)
2. Rename `chooser.bin` to `chooser.app` (GitHub won't let me release a `.app` file)
3. Follow the [normal app installation instructions](https://pocketsprite.com/pages/faq#functionality)