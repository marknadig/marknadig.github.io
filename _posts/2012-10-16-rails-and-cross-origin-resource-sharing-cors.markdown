---
author: marknadig
comments: true
date: 2012-10-16 21:42:33+00:00
layout: post
slug: rails-and-cross-origin-resource-sharing-cors
title: Rails and cross origin resource sharing (CORS)
wordpress_id: 246
tags:
- Ruby on Rails
---

There are a number of posts out there on how to enable CORS requests in your rails apps. For information on CORS here's a good [writeup](http://www.nczonline.net/blog/2010/05/25/cross-domain-ajax-with-cross-origin-resource-sharing/) . I followed [Tom's blog](http://www.tsheffler.com/blog/?p=428) and made the appropriate changes to routes, and my application controller. All was well in the world _except_ with Devise. When a user would fail to authenticate, I'd get the 401 back but no other response data as described in this [SO article](http://stackoverflow.com/questions/11177079/how-to-send-cors-headers-with-devise-if-user-not-authorized-401-response). Basically, Warden was sending back the response before my CORS headers could be set. Then I found the wonderful Rack CORS middleware gem by Calvin Yu [https://github.com/cyu/rack-cors](https://github.com/cyu/rack-cors) which made is super-simple to configure CORS and be intercepted before Warden. Note, if you have trouble with the order the middleware are loaded, see this ticket from Jean Mertz https://github.com/nov/rack-oauth2/issues/18 where he specified the load order with

    
    config.middleware.insert_before Warden::Manager, Rack::Cors


OSS is such a great place to work :)
