---
author: marknadig
comments: true
date: 2011-07-15 14:32:40+00:00
layout: post
slug: virtualbox-disk-deframenting
title: VirtualBox disk deframenting
wordpress_id: 26
tags:
- Virtualization
---

Assuming an windows image, first run defragger:  

http://www.mydefrag.com/  

  

Zero freespace w/ sdelete available from http://technet.microsoft.com/en-us/sysinternals/bb897443.aspx  

sdelete -c   

  

From command/terminal:  

VBoxManage modifyhd diskname.vdi --compact  

  

Thanks:
http://www.processworks.de/blog/2010/07/how-to-shrink-a-virtualbox-vdi-disk-image-to-the-required-size/

