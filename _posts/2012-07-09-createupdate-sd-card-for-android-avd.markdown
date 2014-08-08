---
author: marknadig
comments: true
date: 2012-07-09 22:19:55+00:00
layout: post
slug: createupdate-sd-card-for-android-avd
title: Create/update SD card for Android AVD
wordpress_id: 205
tags:
- Android
---

In an earlier [post](http://blog.nadigs.net/mark/2012/06/25/getting-photos-into-the-gallery-on-android-avd/) I described how to create and copy files to a virtual SD card. I found another good article on how to easily create and copy files to a virtual SD card for Android AVDs. [http://www.tylerfrankenstein.com/create-android-emulator-sd-card-and-write-data-to-it](http://www.tylerfrankenstein.com/create-android-emulator-sd-card-and-write-data-to-it)

Skinny:

Create SD card

    
    tools/mksdcard 100MB mysdcard.iso


Attach SD card to an AVD and launch tools/ddms and the AVD. From DDMS select Device -> File Explorer.

DDMS is also the handy tool I blogged about for [grabbing a screenshot from Android](http://blog.nadigs.net/mark/2012/05/05/grabbing-an-android-screenshot/).
