---
author: marknadig
comments: true
date: 2013-03-11 16:44:30+00:00
layout: post
slug: drying-up-rspec
title: DRYing up RSpec
wordpress_id: 340
categories:
- Ruby on Rails
- testing
---

Today I had the need to run the same set of tests with just one or two variable changes, specifically testing our RESTful routes with a different platform key (web, api, mobile). It didn't feel right to make this a shared example ("it behaves like..."). I came across this [blog post](http://testdrivenwebsites.com/2011/08/17/different-ways-of-code-reuse-in-rspec/) and found the suggestion under "Constructing RSpec examples programmatically" to be exactly what I need


    describe myController, :type => :controller do
      [:api, :mobile, :web].each do |platform|
    
    ...
    end
