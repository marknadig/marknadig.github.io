---
author: marknadig
comments: true
date: 2011-10-27 21:35:18+00:00
layout: post
slug: virtualbox-resize-partition
title: VirtualBox resize partition
wordpress_id: 23
tags:
- Virtualization
---

Best tip is to just create a large (300GB) dynamically sized disk doesn't take up 300GB, it will just grow that large. So, it is best to pick a large size up front. I made the mistake of being too conservative with a XP VMDK and needed to resize it.  

  

Summary:  

Create new disk (Settings: Storage) with large, dynamic size.  

vboxmanage clonehd  old.vmdk new.vmdk --existing  

change VM to use new vmdk as primary  

open host and tell it to use new space.  

  

http://justintung.wordpress.com/2011/01/06/resize-and-expand-a-virtualbox-hard-drive-and-media-made-easy/  

  

Captured copy of article here  

http://home.deltek.com/personal/marknadig/Blog/Lists/Photos/ResizeVMDK.pdf

