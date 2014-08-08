---
author: marknadig
comments: true
date: 2014-08-08 13:58:01-0600
layout: post
slug: blog-migration
title: Blog Migration
---

I'm still cleaning up my migration from WP to Jekyll. Today I had to remind me self how to write [IIS Rewrite Rules](http://www.iis.net/learn/extensions/url-rewrite-module/creating-rewrite-rules-for-the-url-rewrite-module) so any existing blog links wouldn't be broken; e.g.
`http://blog.nadigs.net/mark/2011/02/18/more-android-love/`.

The next hurdle I ran into is that Jekyll wants to force posts under any categories; e.g.

My Post `http://mark.nadigs.net/2011/02/18/more-android-love/` wanted to only be accessible from `http://mark.nadigs.net/android/2011/02/18/more-android-love/` due to the 'Android' category. The simple fix here was to change all categories to tags.

Remaining:

1. add search
2. add tags filter
3. add SO / GH feeds