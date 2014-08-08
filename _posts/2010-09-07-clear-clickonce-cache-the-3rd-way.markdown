---
author: marknadig
comments: true
date: 2010-09-07 18:23:56+00:00
layout: post
slug: clear-clickonce-cache-the-3rd-way
title: Clear clickonce cache, the 3rd way
wordpress_id: 63
tags:
- Work
---

I stumbled across this alternate way to clear the clickonce cache in the comments in this [old blog post](http://bombayboy.wordpress.com/2006/07/03/clear-clickonce-cache/). From a command prompt:

rundll32 dfshim CleanOnlineAppCache

I usually run mage -cc from a _visual studio command prompt_. However, not all QC/design folk have VS.

Since migrating to Windows 7 I've purged the memory of the specific folder where clickonce is stored since this differs from XP. The first two approaches are more resilient.
