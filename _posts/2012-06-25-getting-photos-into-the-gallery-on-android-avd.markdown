---
author: marknadig
comments: true
date: 2012-06-25 23:59:38+00:00
layout: post
slug: getting-photos-into-the-gallery-on-android-avd
title: Getting photos into the gallery on Android AVD
wordpress_id: 193
categories:
- Android
---

From android sdk's tools folder run:

    
    android


From Tools menu, Manage AVDs. Select the AVD and click Edit the AVD. to include a 100mb sd card image.

[caption id="attachment_195" align="alignnone" width="199" caption="AVD Edit"][![](http://blog.nadigs.net/mark/files/2012/06/Screen-Shot-2012-06-25-at-5.50.10-PM-199x300.png)](http://blog.nadigs.net/mark/files/2012/06/Screen-Shot-2012-06-25-at-5.50.10-PM.png)[/caption]

Note: Go ahead and bump RAM up to 1gb while you're in here.

Launch the emulator and run this AVD

    
    emulator @myavd


Now there are a couple ways to mount the SD card once the emulator is running. [http://androidforums.com/developer-101/463412-how-access-files-avd-sd-card.html](http://androidforums.com/developer-101/463412-how-access-files-avd-sd-card.html), however I found that the SDK allowed me to :
1. shell into the AVD using adb (which is in platform-tools, not tools).

    
    adb shell


2. Make the appropriate folder

    
    mkdir sdcard/Pictures
    exit


3. Copy a picture from my local file sytem over.

    
    ./adb push ~/Pictures/IMAG0381.jpg sdcard/Pictures


There may have been a way to copy the file over w/ shelling in, but this is another helpful tidbit.
