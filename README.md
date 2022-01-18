# bg-img
Mobile-friendly javascript alternative to background-attachment:fixed for a fixed background image aka "fake" parallax scrolling effect.

Fixed background images aka "fake" parallax background images are static in position, i. e. do not move, while content moves on top when scrolling. In contrast, parallax background images move when scrolling, albeit slower than foreground elements. Please confer https://siteorigin.com/fixed-vs-parallax-background-images/ for details and a visual comparison.

## Why does this repository exist?
I wanted a fixed background image effect as showcased by w3schools (cf. https://www.w3schools.com/howto/howto_css_parallax.asp). However, as noted on w3schools, the effect did not work on mobile devices.

## Features
* Fixed background image or "fake" parallax scrolling effect for background images
* Alternative to or replacement for "background-attachment: fixed" on mobile devices
* Multiple background images can be cascaded
* Handles resize events including address bars on mobile devices 
* Tested on Windwos 11: Chrome, Firefox
* Tested on iOS: Firefox, Safari
* Tested on Android: Chrome

## Setup
* Download "bg-img.css" and "bg-img.js"
* Include "bg-img.css" in the header of your HTML file
* Include "bg-img.js" at the very end of the body in your HTML file

## Technologies
This project uses CSS and plain Javascript

## How it works
Please confer index.html for a short, hands-on example. Backgorund images are a courtesy  of https://unsplash.com/.

The background images are set to cover the full viewport and are stacked on top of each other. A user-defined z-index determines their order. Within their content, the user defines breakpoints beyond which scrolling will start to reveal the next, i. e. underlying, background image. This is done by listening to the scroll event in Javascript and dynamically adjusting the hight(s) of the currently visible background image(s).

* Breakpoints are determined by looking for divs with class ".bg-img-fixed-breakpoint". divs used a breakpoint can be of height zero or contain content. In the latter case, the breakpoint is at the vertical middle of the div.
* Background images must be placed in an outer div with classes ".bg-img-fixed" and ".z-\*", where \* determines the z-index and as such the order of the images in the stack. An inner div of class ".resize-wrapper" is needed for dynamic resizing on scroll. Example: <blockquote><div class="bg-img-fixed z-1"><div class="resize-wrapper"><img src="..."></div></div></blockquote>
