---
author: marknadig
comments: true
date: 2010-07-22 19:44:03+00:00
layout: post
slug: find-unused-resource-strings
title: Find unused resource strings
wordpress_id: 71
categories:
- Work
---

This handy tip lets the compiler warning you of any unused resource string references. Credit this [blog](http://social.msdn.microsoft.com/Forums/en-US/csharpide/thread/a833e7fb-d18f-44c3-a1f1-dd9bb00abeec).




 




Resources.Designer.cs file:  
  
(1) Turn on Code Analysis warning CA1811  
(2) In your Resources.Designer.CS file comment out the following lines:  
     [global:: System.CodeDom.Compiler.GeneratedCodeAttribute( ...  
     [global:: System.Runtime.CompilerServices.CompilerGeneratedAttribute()]  
(3) Change the class to a static class by putting the word "static" in front of "class":  
     internal static class Resources {  
(4) Comment out the default constructor.  
(5) Compile your program. Now you should be warned about any unused resources.  
(6) Remove your unused resources. (Changing any resources will regenerate the Resources.Designer.cs file.)  
  





**Category:** Work




**Published:** 7/22/2010 3:42 PM



