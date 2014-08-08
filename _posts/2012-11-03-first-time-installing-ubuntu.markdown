---
author: marknadig
comments: true
date: 2012-11-03 02:19:35+00:00
layout: post
slug: first-time-installing-ubuntu
title: First time installing ubuntu
wordpress_id: 254
tags:
- ubuntu
---

I decided to install ubuntu on a my lenovo t410 that already has Win7 and 8. Easy peasy, right?


## Installing


Well, first clean up and defrag the windows partition so I can shrink it. ~30gb allocated now.

I then downloaded 12.10 from [unbuntu.com](http://www.ubuntu.com/download/help/create-a-usb-stick-on-windows) and put it on my thumb drive and booted off that. The installation steps were pretty straight forward. I selected the newly created partition (thankfully keyed of the partition size since I couldn't easily map the /dev/sda1 that ubuntu was showing me to windows drive letters).

When prompted for a mount point [stack exchange](http://superuser.com/questions/423524/what-is-the-correct-mount-point-for-installing-ubuntu-in-its-own-partition-alon) to the rescue. "/" root.

Once it was installed it hijacked the windows boot loader w/ grub. Reverting that was pretty easy - again [stack exchange](http://askubuntu.com/questions/124627/wiped-ubuntu-files-bootloader-still-there-how-can-i-remove-it-and-restore-wind) to the recue with "boot-repair" for ubuntu.

Now on the windows side, just needed to install [EasyBCD](http://neosmart.net/EasyBCD/) to configure the windows boot loader to recognize the ubuntu partition. This is great, I now have my windows boot loader... but when I select ubuntu, I get the grub menu with its own list and 10s countdown :/   This [walkthrough](http://www.ubuntugeek.com/use-the-windows-bootloader-to-dual-boot-windows-vista-and-ubuntu.html) helped me edit grub to just go right into ubuntu.


## Now What


All in all it was very straight forward. It helped a lot to have my mac nearby to google as problems arose. Now that it is installed, I need to run through the "[important things to tweak](http://www.noobslab.com/2012/10/important-thingstweaks-to-do-after.html)" list and I should be golden. Then, webstorm, LAMP and we'll see from there.
