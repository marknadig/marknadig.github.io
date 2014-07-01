---
author: marknadig
comments: true
date: 2013-10-09 15:56:57+00:00
layout: post
slug: chromecast-and-cisco-e3000-problem-fix
title: Chromecast and Cisco E3000 problem fix
wordpress_id: 636
categories:
- Chrome
---

I finally got around to setting up my shiny new Chromecast. The instructions indicate "3 easy steps": 1. plug it in, 2. switch input, 3. set it up. The last part of setup, the Chromecast tries to connect to the wireless network. It failed and I was directed to a KB that no longer exists, but found in cache:

https://support.google.com/chromecast/answer/3213084


<blockquote>

> 
> # Learn More: AP Isolation is enabled
> 
> 
</blockquote>







<blockquote>Your Wi-Fi network configuration prevents devices from communicating with Chromecast. In order to resolve this issue, you will need to disable AP (access point) isolation, also known as client isolation, on your router. Please refer to your router documentation to learn how to disable AP isolation.

If you do not have access to your router settings, or if you are attempting to connect through a guest, hotel or public network with AP/client isolation, you will be unable to set up your Chromecast.

If you are attempting to connect through a Wi-Fi extender, please check your extender settings. You will need to disable AP isolation on your Wi-Fi extender before setting up Chromecast to work with your Wi-Fi network.</blockquote>





I confirmed that AP Isolation was diabled on the router. I searched around and found [another user had run into this](http://mattstard.com/google-chromecast-cisco-e3000-router-fix/) and his solution was to install ddwrt on the e3000. I was reluctant to potentially take down my home network, so reached out to Google support. Their response identified the root cause which is the e3000 is a dual band router and Chromecast only works with the 2.4GHz band.  So, giving each band a unique SSID solved my issue. Interestingly, I found the Google has already updated their docs w/ this possible cause: [ https://support.google.com/chromecast/answer/3228330?hl=en](https://support.google.com/chromecast/answer/3228330?hl=en)
