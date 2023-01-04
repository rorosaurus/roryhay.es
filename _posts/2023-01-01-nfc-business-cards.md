---
layout: post
title: $2 DIY custom NFC business cards!
date: 2023-01-01 13:32:20 +0300
description: Help the environment and your hustle! # Add post description (optional)
img: blog/nfc-business-cards/nfc-business-card.jpg # Add image post (optional)
fig-caption: Just tap their phone to exchange your information!  # Add figcaption (optional)
tags: [Maker, Laser, NFC]
---

For my latest job hunt, I decided to do away with single-use business cards altogether! I just want to make **one** and carry it with me.

For about $2/card, you can DIY your own low volume, homemade smart business cards! Scan the card with any phone and my website will open, where you can collect my contact info and read about my projects!

It's classy, sanitary, and environmentally friendly!

{% include video.html 
    file="/assets/img/blog/nfc-business-cards/video-demo.mp4"
    fig-caption="A quick demo of how easy it is!"
    max-width="90%"
    max-height="1000px"
    video-attributes="muted autoplay loop"
%}

## What to keep in mind when buying NFC cards

Personally, I prefer my card to navigate directly to my website, where the user can choose whether download the vCard. (Otherwise they have to import/save/find the contact and navigate to my website from there!) They can also just keep my tab open to read more about me later!

For my project, I bought these NFC cards directly from [AliExpress](https://www.aliexpress.us/item/3256804276946189.html), but you can buy NFC cards from anywhere! They also come in a variety of shapes/sizes if you don't specifically want a business card.

The two most popular types of NFC cards you'll encounter are tag213 and tag216. Make sure you use these in your search query! What's the difference between them though?

### tag213
tag213 can store 144 bytes, or a URL up to 136 characters. It's a bit cheaper than tag216, but ideal if you're just storing a short URL. For reference, storing only my URL (https://roryhay.es) requires 23 bytes on the card.

### tag216
tag216 can store 888 bytes, or a URL up to 872 characters. It's a little more expensive than tag213, but ideal if you're storing a long URL or a virtual contact card (vCard). If I write my vCard, it would require 252 bytes for my Name, Phone, Email, Website, and a small Note, requiring tag216.

## Programming the card

I personally used [TagWriter](https://play.google.com/store/apps/details?id=com.nxp.nfc.tagwriter&gl=US) on my Android device. You should be able to install many third party NFC read/writing apps from your app store to write the desired information to your card!

## Etching the card

Since I knew I wanted to etch my card with my laser, I went with the black walnut veneer. The darker pigment will allow the material to absorb more laser light (and energy), so I have the best absorption when etching with my small 1 Watt LaserCube.

Check your [local Makerspace](https://makerspaces.make.co/) to see if they have a laser cutter/engraver you can use! Regardless of what laser you use, make sure you know how to use it safely! Ventilation is essential, and laser-specific eye protection too if there is any risk of reflections!

After measuring the dimensions of the card, I designed the card layout in Photoshop, exported as a .png, and imported into LaserOS for raster etching. You'll need to try a few times to find the right balance of laser power and speed, so make sure you have some spares!

*Note: LaserCubes don't give the cleanest results. Since the laser light is arriving on the card at different angles, it's less crisp and focused. You can see the result of this in the thin NFC logo and the smaller phone number text, which is muddied.*

*I'd recommend using a proper full size laser engraver/cutter with a moving XY carriage, if you can find one near you! Then the laser is perfectly perpendicular for the whole engraving! On these lasers, I would recommend starting with low power and high speed, then adjusting the speed lower and power higher with repeated runs on your first card.*

## Good luck!
I can't wait to see what you make!