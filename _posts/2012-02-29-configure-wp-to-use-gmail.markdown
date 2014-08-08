---
author: marknadig
comments: true
date: 2012-02-29 05:17:49+00:00
layout: post
slug: configure-wp-to-use-gmail
title: Configure WP to use gmail
wordpress_id: 7
tags:
- WordPress
---

Nadigs.net email is delegated to google apps. By default, WP uses whatever PHP is configured for which is an smtp server on localhost. Thankfully, there's a plugin for WP that lets use bypass PHP's mail() and go directly to google's smtp service: [http://wordpress.org/extend/plugins/wp-mail-smtp/](http://wordpress.org/extend/plugins/wp-mail-smtp/)
