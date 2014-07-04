---
author: marknadig
comments: true
date: 2012-02-29 05:10:05+00:00
layout: post
slug: installing-wordpress
title: Installing WordPress
wordpress_id: 3
categories:
- WordPress
---

Well, if you're reading this it means I was successful :)

My goal was to install WordPress for multiple blogs. Thankfully 3.x includes a Network feature that supports _n_ blogs and can be based on either sub-domains  (markblog.nadigs.net) or sub-directories (blog.nadigs.net/Mark). My first attempt was the later, but with the added twist of installing WP in a sub-directory to begin with; e.g. www.nadigs.net/blogs/Mark. This seems to be a supported config, and I got primary network site to load, but kept getting 404s on the subsidiary blogs. I think the web.config url rewriting wasn't quite right. So, I scrapped that 1hr of work and decided it was probably best to just host the blog on its own sub-domain and use folders under that.

Basically following this was a breeze: [http://codex.wordpress.org/Installing_WordPress](http://codex.wordpress.org/Installing_WordPress)

And this post was helpful in configuring the network feature (though, don't copy the web.config from here, it has a typeo, use the one from wp's page that comes up when you enable) [http://lauragentry.com/blog/2010/07/30/how-to-create-a-wordpress-3-0-multisite-network-on-a-windows-server-using-sub-directories/#comment-40662](http://lauragentry.com/blog/2010/07/30/how-to-create-a-wordpress-3-0-multisite-network-on-a-windows-server-using-sub-directories/#comment-40662)

So, this is my first blog.
