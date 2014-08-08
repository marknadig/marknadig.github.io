---
author: marknadig
comments: true
date: 2012-11-15 00:10:40+00:00
layout: post
slug: left-outer-join-with-arel
title: LEFT OUTER JOIN with ARel
wordpress_id: 272
tags:
- Ruby on Rails
---

Found [this post](http://ruby.ryanbigg.com/post/1468788928/left-outer-join-with-arel) very helpful, so bookmarking here on my blog.

Basic idea is to use .includes(:assoc) instead of joins. [Squeel](https://github.com/ernie/squeel) supports a little cleaner DSL so you can do .join(:assoc.outer)


