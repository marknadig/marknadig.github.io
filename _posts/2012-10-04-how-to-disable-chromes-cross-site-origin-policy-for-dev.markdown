---
author: marknadig
comments: true
date: 2012-10-04 01:03:30+00:00
layout: post
slug: how-to-disable-chromes-cross-site-origin-policy-for-dev
title: How to disable Chrome's cross site origin policy (for dev)
wordpress_id: 243
categories:
- Chrome
- OS X
---

Running yeoman on port :3031 trying to hit my local test server on :3000 and am stopped due to same origin policy. Here's how circumvent (for local dev only)

    
    open -a Google\ Chrome --args --disable-web-security


[http://stackoverflow.com/questions/3102819/chrome-disable-same-origin-policy](http://stackoverflow.com/questions/3102819/chrome-disable-same-origin-policy)
