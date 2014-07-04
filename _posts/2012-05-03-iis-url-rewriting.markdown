---
author: marknadig
comments: true
date: 2012-05-03 16:50:32+00:00
layout: post
slug: iis-url-rewriting
title: IIS URL rewriting
wordpress_id: 137
categories:
- IIS
---

A friend pointed out paged navigation was busted on my blog. Found that if you came in to the sub-blog w/ no trailing slash, the nav links were incorrectly re-nesting; e.g. /mark/mark/page2. Updating the url rewriting was pretty straightforward

rule: ^mark$
redirect: {R:0}/

[http://learn.iis.net/page.aspx/460/using-the-url-rewrite-module/](http://learn.iis.net/page.aspx/460/using-the-url-rewrite-module/)
