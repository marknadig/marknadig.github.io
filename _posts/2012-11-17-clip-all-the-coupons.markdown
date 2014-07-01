---
author: marknadig
comments: true
date: 2012-11-17 15:43:52+00:00
layout: post
slug: clip-all-the-coupons
title: clip all the coupons
wordpress_id: 274
---

Local grocer has a page with special offers. It is a pain to go through and click each one to 'add', so came up with this to automate:

First, no jquery, so add it to the page:

    
    var script = document.createElement("script");
    script.type = "text/javascript";
    script.src = 'http://code.jquery.com/jquery-1.8.3.min.js';
    script.text = "alert('voila!');" // use this for inline script
    document.body.appendChild(script);


Now, find all the items (not already clipped) and clip

    
    $(".lt-offer").not(".lt-clipped").find(".lt-add-offer-link").each(function(one, two) { two.click()})


Alternate selector:

    
    $(".lt-offer-list-item").not(".lt-clipped").find(".lt-add-offer-link").each(function(one, two) { two.click()})

