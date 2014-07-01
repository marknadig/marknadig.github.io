---
author: marknadig
comments: true
date: 2012-05-17 22:06:07+00:00
layout: post
slug: android-emulator-on-osx-lion
title: Android emulator on OSx (Lion)
wordpress_id: 176
categories:
- Android
---

Install SDK as described in my [prior post](http://blog.nadigs.net/mark/2012/05/05/grabbing-an-android-screenshot/). Open terminal and go to the tools folder beneath you extracted the sdk (~/Code/android-sdk-macosx/tools)

To create a virtual device:

    
    ./android create avd -n <em>NAME</em> -t 1


**_NAME_** - the vm name.
**_-t #_** - the target level.  (1 = 2.1, 2 = 2.2, 3 = 2.3.3 ...)

To list available targets:

    
    ./android list targets


Launch emulator for given **_NAME_** device:

    
    ./emulator @<em>NAME
    </em>  # or<em> 
    </em>./emulator -avd<em> NAME </em>
    List devices:
    ./android list avd







Start ddms before you launch the emulator to attach.


thanks to [http://blog.brightpointuk.co.uk/running-google-android-emulator-macos](http://blog.brightpointuk.co.uk/running-google-android-emulator-macos) for starter for this
