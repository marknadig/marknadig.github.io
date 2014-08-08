---
author: marknadig
comments: true
date: 2013-08-09 15:29:45+00:00
layout: post
slug: ruby-regex-end-of-line-character-different-depending-on-platform
title: Ruby regex end of line character different depending on platform
wordpress_id: 496
tags:
- regex
- Ruby
---

Ruby's IO.puts will use the appropriate separator based on the platform; e.g. "\n" for *nix and "\r\n" for windows, which makes sense to me. However, ran into an issue today where the end line character for regex wasn't matching as demonstrated here (tested on OSX)

    
        > s = "test\r\nhere"
        > s.match(/test$/)
         => nil


I found this SO article helpful:
[http://stackoverflow.com/questions/5148359/ruby-on-a-mac-regular-expression-spanning-two-lines-of-text](http://stackoverflow.com/questions/5148359/ruby-on-a-mac-regular-expression-spanning-two-lines-of-text)

I ran into this because I had to change the Ri_Cal gem to export using DOS style \r\n always per [http://tools.ietf.org/html/rfc2445#section-4.1](http://tools.ietf.org/html/rfc2445#section-4.1). The spec tests were failing because they were just using "$' to match the end of line, which now was an "\r". In my case, I just added the "\r" so that someone coming behind me would be clear on the intent. Another approach would be to strip before I tested (let that image sink in).
