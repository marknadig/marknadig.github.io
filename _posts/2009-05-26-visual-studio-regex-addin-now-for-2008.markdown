---
author: marknadig
comments: true
date: 2009-05-26 19:10:01+00:00
layout: post
slug: visual-studio-regex-addin-now-for-2008
title: Visual Studio Regex addin (now for 2008)
wordpress_id: 62
categories:
- Work
---

Visual Studio's regex implementation is non-standard. Thankfully, there's an open source add-in for VS2008 that allows you to use "standard" regular expressions found [here](http://www.codeproject.com/KB/macros/VS2008RegexAddIn.aspx).

“Why do I care?” Here’s a very useful example of why regex is so cool: Say you wanted to replace all calls to a function, like IsNothing(…) and replace it with a native sytnax … Is Nothing  (and Not IsNothing(…) with … IsNot Nothing)

You can just use this search string (set ignore pattern whitepace):

`(?Not(?:\s))?IsNothing\((?(?>[^()]+|\((?)|\)(?))*(?(number)(?!)))\)`

Expanded:
```
(?Not(?:\s))?  
IsNothing\((?  
    (?>  
        [^()]+   
        |    \( (?)  
        |    \) (?)  
    )*  
    (?(number)(?!))  
    )  
\)
```

With this replace string:
`${inner} Is${prefix} Nothing`

