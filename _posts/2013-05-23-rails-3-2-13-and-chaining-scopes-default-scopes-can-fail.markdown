---
author: marknadig
comments: true
date: 2013-05-23 22:25:41+00:00
layout: post
slug: rails-3-2-13-and-chaining-scopes-default-scopes-can-fail
title: 'Rails 3.2.13 and default scopes fail '
wordpress_id: 485
categories:
- Ruby on Rails
---

Rails upgrade SOP - created a branch, upgraded from 3.2.12 to 3.2.13, ran tests and... WAT?... a number of failures. My controller tests were telling me they are getting data they shouldn't. Root cause was identified as this issue: [https://github.com/rails/rails/issues/9813](https://github.com/rails/rails/issues/9813)

Bottom line is if you have default scopes on your model, subsequent scoping appears to ignore it.; e.g.
[code language="ruby"]
    class Book < ActiveRecord::Base
      default_scope where(:id => [1,2])
    end
    
    bs = Book.all #  SELECT "books".* FROM "books" WHERE "books"."id" IN (1, 2)
    bs.find(3) # SELECT "books".* FROM "books" WHERE "books"."id" = ? LIMIT 1  [["id", 3]]
[/code]

In 3.2.12 would raise RecordNotFound, 3.2.13 happily finds it. So, waiting on a fix for that. Seems not an easy fix :/
