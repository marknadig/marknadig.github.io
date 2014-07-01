---
author: marknadig
comments: true
date: 2013-10-15 21:40:17+00:00
layout: post
slug: chkdsk-r-wouldnt-on-reboot
title: chkdsk /R wouldn't on reboot
wordpress_id: 638
categories:
- Windows 7
---

When I would try to run chkdsk /R on my my Windows 7 laptop, it would, of course, say the volume is locked and asked if I wanted to run on reboot. "Yes, of course.", reboot ... nothing. I found this thread helpful:

[http://forum.notebookreview.com/windows-os-software/172250-scheduled-chkdsk-wont-run-reboot.html](http://forum.notebookreview.com/windows-os-software/172250-scheduled-chkdsk-wont-run-reboot.html)

I was not able to run chkdsk from a command prompt from safe mode. I was able to create a recovery DVD, boot to that and run chkdsk from a command prompt.
