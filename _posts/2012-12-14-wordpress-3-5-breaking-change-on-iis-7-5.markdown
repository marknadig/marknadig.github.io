---
author: marknadig
comments: true
date: 2012-12-14 17:27:12+00:00
layout: post
slug: wordpress-3-5-breaking-change-on-iis-7-5
title: Wordpress 3.5 breaking change on IIS 7.5 - download failed...
wordpress_id: 304
tags:
- WordPress
---

I recently upgrade this blog to WP 3.5 and all looked fine. However, when I tried to update the akismet plugin, it would fail with "Download failed. Destination directory for file streaming does not exist or is not writable.."  Most search results indicated a permissions issue, but I hadn't changed any permissions.  Thankfully I found a [post](http://infinitewp.com/forum/issues/download-failed-destination-directory-for-file-streaming-does-not-exist-or-is-not-writable/) related which pointed me to this [defect](http://core.trac.wordpress.org/ticket/22900) with the appropriate workaround. Basically, there was a regression in 3.5 related to what temp folder was used - and even though there's a fix in 3.5.1, it's a chicken and egg problem since downloading 3.5.1 would fail due since pointing to the wrong temp folder.

I added this to my wp-config.php and was able to update the plugin just fine.

    
    define( 'WP_TEMP_DIR', ABSPATH . 'wp-content/' );
