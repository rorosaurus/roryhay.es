---
layout: post
title: Hidden Konami Code JS
date: 2016-04-22 13:32:20 +0300
description: A javascript library to add secret easter eggs to your website! # Add post description (optional)
img: # Add image post (optional)
fig-caption: # Add figcaption (optional)
github-repo: https://github.com/rorosaurus/hidden-konami-js # Add github repo (optional)
tags: [Math, Web]
---

The original [konami-js](https://github.com/snaptortoise/konami-js) is a nice little library that lets you add a secret function to your website which is called when you type in the [Konami Code](https://en.wikipedia.org/wiki/Konami_Code): `↑ ↑ ↓ ↓ ← → ← → B A START`

I love using this to sneak little easter eggs into my projects, but I've always had a few complaints.
* You can't customize the input pattern that reveals the secret
* The correct input pattern and secret function are plainly visible in the page/js source, so they are easy to discover

This fork aims to solve these complaints by:
* Enabling the customization of patterns
* Hiding the desired input pattern and the secret function
 * Verifying a hash of the desired input pattern, not the pattern itself directly
 * The secret function is hidden in a new .js file, whose location is only revealed after the correct input is received

## Why

You want your website to do something special, but you don't want it to be immediately obvious what the desired pattern is upon inspection of the source.  The only way to find the secret is to spread it by word of mouth! (or by finding the website owner and [buying a $5 wrench](https://xkcd.com/538/))

Using the MD5 hash is cheap and good enough for this.  It also comes with the added bonus of seeing if anyone cares about your secret enough to try and find a collision just to find an acceptable pattern!

## Demo

There is a live demo over at https://rorosaurus.github.io/hidden-konami-js/

Can you find all the secret input patterns?  Go ahead!  Open the developer tools!  Inspect the page source!  The only info you have is ````konami.js```` and something in the HTML document like:

```
<script>var easter_egg = new KeyKonami("0a75e752070ffe5ed283de6d81efb3db", 20);</script>
```

So you have an MD5 hash of the desired input pattern and it's length.  Not too much to go on.  So unless the site owner tells you something like:

> Hey you should type 'hello' and see what happens.

..then you are in a tough place, unless you want to start searching for MD5 collisions. :)

*Hint: Okay well this becomes trivial once you realize the demo site contents are public on the [GitHub pages branch](https://github.com/rorosaurus/hidden-konami-js/tree/gh-pages).  Of course, this project is **actually** useful on private webservers which don't allow visitors to view the directory contents. ;)*

## Generator

On the left sidebar of the demo site, I've created a quick tool to help you generate the values you'll need for setup!  Once you settle on a good input pattern, you can save the relevant values.  They are downloaded as a .txt for security reasons, but the file can be renamed and used as the .js file you'll use in step 3!

Note: The Pattern String isn't needed, but I include it so you don't forget your pattern.  For keyboard input, the Pattern String is the [KeyboardEvent keyCode](http://www.w3schools.com/jsref/event_key_keycode.asp).  For touch input, the Pattern String is a comma separated string describing the swipes/taps.

## Setup

**Step 1:** First, you need to add the script to your page.  Make sure you add the MD5 script too!
```
<script type="text/javascript" src="konami.js"></script>
<script type="text/javascript" src="md5.min.js"></script>
```

**Step 2:** Next, attach the easter egg to your site by adding the tag below to your HTML.  You'll need two of the generated values from earlier: the pattern hash and the pattern length.  Create a KeyKonami for a pattern that uses keyboard presses and use TouchKonami for a pattern that uses touch input.
```
<script>var easter_egg = new KeyKonami("pattern_hash", pattern_length);</script>
```

**Step 3:** Finally, you need to create a new  ````js_filename.js```` file (or reuse the file you downloaded from my generator).  Create a function with the name that was generated - then add your easter egg code!  You're done!
```
function function_name(){
    alert("Your secret code goes here!");
}
```

## Tips

* You can use more than one easter egg, just make sure to use a different variable names!
* We assume the .js file is in the same directory as the HTML file.  (You can probably modify the source to change that if necessary.)
* I recommend storing information about the input patterns inside the .js files, so you don't forget the details a few months from now.
    * The generator automatically does  this for you.
* Try daisy chaining these files together!  Build a breadcrumb trail by providing hints in each file for the next secret input pattern - turning your easter eggs into a literal easter egg hunt!

## This is not secure
Nor is it meant to be.  Please **do not use this to secure anything actually important**.  This is just meant to be a simple way to make some dumb secret jokes on your website, which can (mostly) only be discovered or spread by word-of-mouth.  This does not actually protect anything and, as previously mentioned, can be defeated by a determined adversary.

## Thanks

[Original konami-js repo](https://github.com/snaptortoise/konami-js)

[MD5 library repo](https://github.com/blueimp/JavaScript-MD5)

Licensed under the [MIT License](http://opensource.org/licenses/MIT)