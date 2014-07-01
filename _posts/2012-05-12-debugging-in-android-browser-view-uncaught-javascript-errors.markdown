---
author: marknadig
comments: true
date: 2012-05-12 17:06:39+00:00
layout: post
slug: debugging-in-android-browser-view-uncaught-javascript-errors
title: Debugging in android browser - view uncaught javascript errors
wordpress_id: 154
categories:
- Android
---

I was struggling to see why my site wasn't loading on my android browser. Running ddms from the console wasn't helping. Most blog posts suggested littering console.log() throughout the app that would show up in ddms log. Thankfully found this tip on:

[http://stackoverflow.com/questions/2314886/how-can-i-debug-javascript-on-android](http://stackoverflow.com/questions/2314886/how-can-i-debug-javascript-on-android)

navigate to about:debug on the browser which enables more javascript setting. This threw me a bit since it didn't really show me anything. However, what it does do is enable additional settings for javascript. Now, when a page is loaded with script errors, "show javascript console" appears:

[![](http://blog.nadigs.net/mark/files/2012/05/android-300x136.png)](http://blog.nadigs.net/mark/files/2012/05/android.png)

More helpful details here: [http://android.stackexchange.com/questions/5999/android-browsers-aboutdebug-what-do-those-settings-do](http://android.stackexchange.com/questions/5999/android-browsers-aboutdebug-what-do-those-settings-do)

(Note: see [prior post](http://blog.nadigs.net/mark/2012/05/05/grabbing-an-android-screenshot/) on how to grab screen from android)
