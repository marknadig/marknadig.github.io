---
author: marknadig
comments: true
date: 2010-07-22 21:38:51+00:00
layout: post
slug: system-componentmodel-defaultvalueattribute
title: System.ComponentModel.DefaultValueAttribute
wordpress_id: 70
categories:
- Coding
---




I ran into a couple snags today on how to define default values for some properties. Specifically how can I specify the default is **Nothing** (in this case, for a String type property)? 




 




DefaultValue( CStr(Nothing))




DefaultValue( DirectCast(Nothing, String))




 




 




My second problem was how to specify a default for a property with an enumerated type? I tried 




 




DefaultValue( LookupViewType.Standard)  




 




but it still serialized this. The correct syntax is:




 




DefaultValue( GetType( LookupViewType), "Standard")




 




 




**Category:** Coding




**Published:** 7/22/2010 5:23 PM



