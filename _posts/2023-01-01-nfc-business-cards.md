---
layout: post
title: $2 DIY custom NFC Business Cards
date: 2023-01-01 13:32:20 +0300
description: Help the environment and your hustle! # Add post description (optional)
img: blog/nfc-business-cards/nfc-business-card.jpg # Add image post (optional)
fig-caption: Tap your phone, get my info!  # Add figcaption (optional)
github-repo: # Add github repo (optional)
tags: [Maker, Laser, NFC, Web]
---

For my latest job hunt, I decided to do away with single-use business cards altogether! I just want to make **one** reusable, high-tech card and carry it with me!

For about $2/card, you can DIY your own low volume, homemade smart business cards! Scan the card with any phone and my website will open, where you can collect my contact info and read about my projects!

It's classy, sanitary, and environmentally friendly!

{% include video.html 
    file="/assets/img/blog/nfc-business-cards/video-demo.mp4"
    video-attributes="muted controls autoplay loop"
    fig-caption="A quick demo of how easy it is!"
%}

## What to keep in mind when buying NFC cards

Personally, I prefer my card to navigate directly to my website, where the user can choose whether download my virtual contact card. Alternatively, I could embed the contact card itself directly, but then the user would have to import/save/find the contact and navigate to my website from there! With just my website, they can just keep my tab open to read more about me later after the in-person exchange is over!

For my project, I bought [these NFC cards directly from AliExpress](https://www.aliexpress.us/item/3256804276946189.html), but you can buy NFC cards from my vendors online! They also come in a variety of shapes/sizes if you don't specifically want a business card.

The two most popular types of NFC cards you'll encounter are tag213 and tag216. Make sure you use these in your search query! What's the difference between them though?

### tag213
tag213 can store 144 bytes, or a URL up to 136 characters. It's a bit cheaper than tag216, but ideal if you're just storing a short URL. For reference, storing only my URL `https://roryhay.es` requires 23 bytes on the card.

### tag216
tag216 can store 888 bytes, or a URL up to 872 characters. It's a little more expensive than tag213, but ideal if you're storing a long URL or a virtual contact card (vCard). If I write my vCard, it would require 252 bytes for my Name, Phone, Email, Website, and a small Note, requiring tag216.

### tag215
Not super relevant for this project, but I just wanted to mention: tag215 is compatible with [amiibo](https://www.nintendo.com/amiibo/)! You can use them to backup or write amiibo, but you should search for that how-to elsewhere online!

## Etching the card

Check your [local Makerspace](https://makerspaces.make.co/) to see if they have a laser cutter/engraver you can use! Regardless of what laser you use, make sure you know how to use it safely! Ventilation is essential, and laser-specific eye protection too if there is any risk of reflections!

After measuring the dimensions of the card, I designed the card layout in Inkscape, exported as a .png, and sent to the laser for raster etching!

You'll need to try a few times to find the right balance of laser power and speed, so make sure you have some spares! I recommend starting with very low power and high speed, then adjusting the speed lower and power higher with repeated runs on your first card. If you etch too deep, you can expose the antenna traces, which could damage the card and *reflect the laser* so try to avoid that!

## What data to write to your NFC card

What would you like your NFC card to do when someone taps it? Pick one! (First two are my favorites.)

* Open a website URL directly in the browser
* Create a new contact with your information already filled out
* Automatically connect to a Wi-Fi network or Bluetooth device
* Launch an app
* Display some plain text
* And more!

Anecdotal note: iPhones seem to have difficulty scanning NFC tags with more data on them. For highest reliability, I opted to simply open my website, since that is less data to transmit.

## Programming your NFC card

If you can read NFC tags, you can probably program your NFC card with your phone!

* Android 4.0 (Ice Cream Sandwich) introduced NFC in 2011, and the hardware is usually included on most mid-high end phones. Do a quick search if you aren't sure!
* iPhone 7 and later got NFC tag write support in 2014, with iOS 13 or newer.

Here's some apps I can recommend to write the desired tag information/behavior:

### NFC TagWriter by NXP

[Google Play](https://play.google.com/store/apps/details?id=com.nxp.nfc.tagwriter&hl=en_US&gl=US), [Apple App Store](https://apps.apple.com/us/app/nfc-tagwriter-by-nxp/id1246143221)

Pros:
* Works with any field from your contacts app. Include your name, nickname, phone, email, website, notes, and more!

Cons:
* Kind of clunky to use.
* Can't create a new contact from scratch.
    * You MUST have an existing contact with your desired information entered. You can select which fields you want to transfer onto the NFC card.

### NFC Tools by wakdev

[Google Play](https://play.google.com/store/apps/details?id=com.wakdev.wdnfc&hl=en_US&gl=US), [Apple App Store](https://apps.apple.com/us/app/nfc-tools/id1252962749)

Pros:
* Can create a new contact from scratch, manually entering the desired information.
* Can add multiple records to your NFC tag. (eg. Record 1: vCard contact info, Record 2: Open a Website)

Cons:
* Limited contact fields. Only name, company, address, phone, email, and website. No "notes" or other useful fields.
* Cannot import an existing contact without paid version.
* Only the first record is opened by Android/iOS (unless you're using an extra app like this one), so extra records aren't really useful.

## Good luck! I can't wait to see what you make!