---
author: marknadig
comments: true
date: 2010-11-10 18:24:58+00:00
layout: post
slug: building-vs2008-test-project-with-vs2010
title: Building VS2008 test project with VS2010
wordpress_id: 47
categories:
- VS2008
---

First error trying to build a VS2010 test project targeting .NET 3.5 and I ran into this error:

_ Could not load referenced assembly "C:\Windows\Microsoft.Net\assembly\GAC_MSIL\Microsoft.VisualStudio.QualityTools.UnitTestFramework\v4.0_10.0.0.0__b03f5f7f11d50a3a\Microsoft.VisualStudio.QualityTools.UnitTestFramework.dll".  Caught a BadImageFormatException saying "Could not load file or assembly" _

Turns out this is a known issue w/ MSBUILD 4.0 on x64:
[http://blogs.msdn.com/b/madhurig/archive/2009/11/25/building-vs2008-projects-with-tfs-build-2010.aspx](http://blogs.msdn.com/b/madhurig/archive/2009/11/25/building-vs2008-projects-with-tfs-build-2010.aspx)

To workaround I changed the reference to the 9.0 image (VS2008)
