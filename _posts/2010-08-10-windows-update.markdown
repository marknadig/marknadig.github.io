---
author: marknadig
comments: true
date: 2010-08-10 16:21:29+00:00
layout: post
slug: windows-update
title: Windows Update
wordpress_id: 65
tags:
- Windows 7
---

Group policy prevents updates from being installed automatically. So, I periodically like to scan for update myself for my Windows 7 64-bit since it is not officially supported by IT.

I created a schedule task to check for updates: wuauclt /ShowWUAutoScan

Note: Most articles I've read suggest wuauclt /detectnow however, I didn't have any luck with that.

List of switches

[http://www.msfn.org/board/topic/143031-windows-update-wuapp-switches-are-there-any/](http://www.msfn.org/board/topic/143031-windows-update-wuapp-switches-are-there-any/)

[http://technet.microsoft.com/en-us/library/cc720477(WS.10).aspx](http://technet.microsoft.com/en-us/library/cc720477(WS.10).aspx)
