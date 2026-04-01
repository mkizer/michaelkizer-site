---
title: Desktop Tour 2023
author: Michael Kizer
pubDatetime: 2023-01-18T15:00:00Z
# modDatetime: 2026-03-31T14:43:00Z
# slug: desktop-tour-2023
featured: true
draft: false
tags: 
  - tech
  - windows
description:
  A look at my home office computing configuration for 2023.
---

Here's a tour of my current home office setup as of January 2023. Over the years it has gone through many iterations - triple monitors, many machines connected via complex KVM switching, etc. The current state is the result of stripping down the overly complex setup, going too far, and then adding a few things here and there. I've been running with the current configuration for a few months now, and I really like it.<!--more-->

This setup is used for both personal and work computing. Since the start of the pandemic in early 2020, I've been just about 100% working from home. So, having a setup that satisfied both needs was vital.

![Desk 2023](@/assets/images/desk2023-scaled.jpg "Desk 2023")

The real centerpiece is the Dell 38" ultra-wide monitor ([U3818DW](https://www.dell.com/en-hr/work/shop/cty/pdp/spd/dell-u3818dw-monitor)). This monitor has a maximum resolution of 3840 x 1600, so it has a bit of a taller aspect ratio than other ultra-wides, which is good for more vertical content. The width of this screen is also perfect for viewing two full-size applications side-by-side. The major selling point for this monitor is the fact that it has built-in [KVM](https://en.wikipedia.org/wiki/KVM_switch), allowing the connection of up to three computers that can all share the same keyboard, mouse, and related USB peripherals. Switching between computers can be achieved by using the front panel buttons on the monitor or configuring Dell's Display Manager Software to use keyboard shortcuts. 

Switching between monitor inputs on the U3818DW also switches any USB peripherals connected to the monitor's "downstream" USB ports (an "upstream" USB cable connects each computer to the monitor). I currently have my keyboard, mouse, and webcam connected to the monitor, so they are shared among any connected computers. The audio from all shared computers is also routed to the monitor and then sent out to the Mackie Powered Studio Monitors ([CR3](https://mackie.com/en/products/studio-monitoring/cr-x-series/CR3_X.html) - note: this link is to a newer model) to the left and right of the monitors. Only the audio from the currently active computer is passed thru to the speakers.

One of the computers that I have connected is the HP 360 Chromebook on the left of the main monitor via a single USB-C cable, which handles all communication and power needs. I have the laptop on an adjustable arm ([amazon.com](https://amzn.to/3w4KKYe)) to allow me to use the screen, as well as access the keyboard when I am using other systems. The end of the arm is a special laptop tray that holds the laptop securely in a variety of positions.
![Laptop Arm](@/assets/images/laptoparm.jpg "Laptop Arm") 

I typically use local audio on the Chromebook and keep it running throughout the day to play podcasts and videos while I work on the other computers. I was evaluating using Chrome OS as a main desktop environment, and it does work nicely on the big screen, but there were just a few applications and pieces of hardware that I couldn't live without. This position in the setup also makes it possible to swap out the Chromebook for any other laptop that supports a single USB-C connection. So, I can swap out laptops with a single cable swap, place one on the monitor arm if needed, view it on the big screen, and have instant access to the keyboard, mouse, and other peripherals. It's very handy.

Also connected to the U3818DW are my home desktop computer (something I built back in 2014 that is still cranking along) and my work laptop. The desktop resides on a CPU shelf that is mounted to the underside of the desk, while the work laptop sits on a small shelf behind the main U3818DW monitor along with a docking station that connects it to the monitor and makes it easy to unplug the laptop for that rare trip to the office.

The monitor on the right side is my older Dell 27" ([U2713HM](https://www.dell.com/il/en/business/p/dell-u2713hm/pd))  configured in portrait orientation. It is connected to both my home and work computers. With this portrait configuration, the maximum resolution is 1440 x 2560. It is great for work in order to keep my Microsoft Teams chat open at the top 1/3rd and still have space for a full document page or website on the bottom 2/3rds. For my home computer, I usually have social feeds ([Mastodon](https://joinmastodon.org/), [Tweeten](https://tweetenapp.com/), etc.) or videos open, leaving the main monitor fully available for everything else. The only downside to this is that switching this monitor between computers has to be handled separately from the main monitor, via input buttons on the front of the U2713HM. Not too terrible, but if it also supported USB "upstream" connections, it's possible it would work with the Dell Display Manager software and be made to switch along with the other monitor.

![Microsoft PowerToys](@/assets/images/powertoys.png "Microsoft PowerToys")
If you are using large or multiple monitors, a good tool for Windows users is Fancy Zones (part of the [PowerToys](https://github.com/microsoft/PowerToys) collection). This application will let you define screen layouts to make good use of your screen real estate. It's like an expanded version of the built-in window handling (called [Snap](https://support.microsoft.com/en-us/windows/snap-your-windows-885a9b1e-a983-a3b1-16cd-c531795e6241#:~:text=To%20optimize%20your%20screen%20space,or%20the%20Snap%20Assist%20feature.)). I use a combination of both. For example, you can use Snap to move and resize a window to the left or right half of the screen by using the mouse or Win + Left/Right Arrow keys. This is great for dividing the ultra-wide screen monitor in half and running two applications side-by-side. I also use Fancy Zones to define a center-focused configuration, with a single wider pane in the middle, flanked by smaller windows along the sides. I also divide the portrait monitor into thirds to fit three apps stacked upon each other (also the 1/3 - 2/3 configuration mentioned earlier). Fancy Zones (along with the other tools in PowerToys) are some pretty powerful additions to your toolkit.

The main peripherals shared between all three computers are the [Kinesis Freestyle Edge RGB](https://gaming.kinesis-ergo.com/edge/) split ergonomic mechanical keyboard, the [Logitech MX Master 3](https://www.logitech.com/en-us/products/mice/mx-master-3s.910-006556.html) mouse, and a [Logitech C920 HD Pro Webcam](https://www.logitech.com/en-us/products/webcams/c920s-pro-hd-webcam.960-001257.html?&utm_source=google&utm_medium=cpc&utm_campaign=Logitech%20-%20Personal%20Collaboration%20-%20DTX%20-%20Webcam%20MID%20-%20Webcams%20-%20ROAS%20-%20US&gclid=Cj0KCQiAiJSeBhCCARIsAHnAzT_Ukm7zCfqthrHoOeUA10EKKC6eXnzQkJPM9rbnqiY3NZl1KsSZ9LMaAhVXEALw_wcB) which sits below the main monitor and sports a physical security cover (I don't really use the webcam if at all possible).

![Kinesis Freestyle Edge RGB keyboard](@/assets/images/keyboard.jpg "Kinesis Freestyle Edge RGB keyboard")
The keyboard is an interesting split design to allow your hands to reside about shoulder-width apart for comfort. It took a little bit to get used to, but now it's hard to go back to a cramped laptop keyboard. The keyboard also supports some programmability (an additional layer, macros, rearranging keys, custom lighting, etc.). All of this configuration is stored on the keyboard itself, so it carries across to any computer it is connected to, which is great for this type of setup. One downside to using this particular keyboard with the built-in KVM on the main monitor is that there is about a 10-second pause before the keyboard is recognized when switching computers. This would be a show-stopper if I switched back and forth constantly, but I only switch very occasionally (like after a workday, I'll switch to the home computer just so I'm not tempted to keep checking email and such).

I've also recently started experimenting with the placement of the mouse, moving it from the normal right side of the keyboard to the center space between the two halves. It's a much shorter distance to reach, but it did take a couple of weeks to override my muscle memory and stop grabbing air to the right of the keyboard.

![Ikea Galant Desk](@/assets/images/desk.jpg "Ikea Galant Desk")
The desk is an old Ikea Galant (no longer available). A spaciously large "L" shape (7.5' x 6.5'), very sturdy steel with a thick manufactured wood top. The file cabinet is a separate piece on wheels, so it can be moved from under the desk for more legroom. The CPU holder is on the right, bolted to the underside of the desk, and is capable of supporting even very large tower computers. I built the free-standing shelves sitting on top of the desk from some Ikea wall shelving and short legs that were from some other Ikea collection. There is another small half-circle-shaped shelf with the same legs, that sits behind the main monitor (to hide my work laptop and docking station). Ikea has some great stuff you can hack together to make their furniture even more useful. 

That about wraps up the desk tour for this year. Let me know if you have any questions about it.

---

#### By the way, the artwork on the walls is as follows:

![Narcosis (1987)](@/assets/images/narcosis.jpg "Narcosis (1987)")
> Narcosis (1987) framed. This is an "artist proof" on canvas that [Ioannis (Dangerousage)](https://dangerousage.com/) sent me several years ago. This painting would become the cover for the [Fates Warning](http://fateswarning.com/) album "Awaken The Guardian".

![Cover art for the album Dead End Kings by Katatonia. By Travis Smith (signed print)](@/assets/images/DeadEndKings.jpg "Cover art for the album Dead End Kings by Katatonia. By Travis Smith (signed print)")
> Cover art for the album Dead End Kings by [Katatonia](https://katatonia.com/) (signed print). By [Seempieces - The Art of Travis Smith](https://www.seempieces.com/)
