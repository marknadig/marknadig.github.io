---
author: marknadig
comments: true
date: 2010-07-14 23:19:05+00:00
layout: post
slug: uninstalling-the-hard-way
title: Uninstalling the hard way
wordpress_id: 72
categories:
- Work
---

As I was trying to clean up my XP "home server", I noticed SQL Server Express 2005 was still installed from back when I had my own mail server. Opening Add/Remove programs, I was surprised to find no Remove option:


![](/images/broken_image.jpg)

 

This was a bit disconcerting… Thankfully you can find everything on the web and this old [blog post](http://blogs.msdn.com/b/astebner/archive/2005/07/01/434814.aspx) from 2005 walked me through running [MSIINV](http://cid-27e6a35d1a492af7.skydrive.live.com/self.aspx/Blog|_Tools/msiinv.zip) to get the product GUID and manually uninstalling from a command-line; e.g.


msiexec /x {2AFFFDD7-ED85-4A90-8C52-5DA9EBDC9B8F}

**Category:** Work

**Published:** 7/14/2010 7:19 PM

