---
author: marknadig
comments: true
date: 2013-02-28 18:10:26+00:00
layout: post
slug: nexus-4-android-debugging-usb-file-transfer
title: Nexus 4 - Android debugging, USB file transfer
wordpress_id: 327
tags:
- Android
---

Trying to do a little debugging on my new Nexus 4. Step 1. enable USB debugging. Where'd it go!? Well, it is hidden now:  [http://developer.android.com/tools/device.html](http://developer.android.com/tools/device.html)


"**Note:** On Android 4.2 and newer, **Developer options** is hidden by default. To make it available, go to **Settings > About phone** and tap **Build number** seven times. Return to the previous screen to find **Developer options**."


Second, where can I enable just USB disk? By default it is shared as a media device.

**Settings -> Storage -> options -> USB computer connection -> Connect as** ... check **Camera (PTP)**.

**[update]**

Turns out that didn't let me transfer files either on my Mac :/ Had to download the Android file transfer app.

_[http://support.google.com/nexus/bin/answer.py?hl=en&answer=2812526](http://support.google.com/nexus/bin/answer.py?hl=en&answer=2812526)_

__[http://www.android.com/filetransfer/](http://www.android.com/filetransfer/)__
