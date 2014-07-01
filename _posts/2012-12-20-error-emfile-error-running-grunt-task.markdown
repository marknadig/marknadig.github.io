---
author: marknadig
comments: true
date: 2012-12-20 16:22:23+00:00
layout: post
slug: error-emfile-error-running-grunt-task
title: 'Error: EMFILE... error running grunt task'
wordpress_id: 308
tags:
- launchctl
- ulimit -n
---

I was running into EMFILE errors running my grunt task for Angular dev. Seems the root cause was a limit on the maximum # of files open. [SuperUser](http://superuser.com/questions/302754/increase-the-maximum-number-of-open-file-descriptors-in-snow-leopard) for the win.


