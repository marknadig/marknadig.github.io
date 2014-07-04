---
author: marknadig
comments: true
date: 2012-12-21 16:38:35+00:00
layout: post
slug: test-if-date-ranges-overlap
title: Test if date ranges overlap
wordpress_id: 313
categories:
- Coding
---

Every time I need to test to see if two date ranges overlap, I reference this [post](http://c2.com/cgi/wiki?TestIfDateRangesOverlap). Since I haven't really internalized it yet, I thought I'd better bookmark it here and just in case the link ever goes away, here's the text

**Problem:** Given two date ranges, each with start and end dates (and possibly times), how do you determine if the ranges overlap?

**Solution:**

Testing the range "start1 to end1" against the range "start2 to end2" is done by testing if...

    
    	<strong>( start1 <= end2 and start2 <= end1 )</strong>


If TRUE, then the ranges overlap. If the ranges do not include the "end" value itself, then use "<" instead of "<=" in the comparisons.

**Important Assumption:**

This assumes that start date <= end date in each range. This can also be stated as...

    
    	<strong>( start1 <= end1 and start2 <= end2 )</strong>


For discussion of what to do if this is not true, see below.

**Applicability:** Is not limited to date/time comparisons; can also be used for ranges of numbers, names, and any other data type where ranges are meaningful.

**Alternate Expression:**

    
    	<strong>not (end1 < start2 or end2 < start1)</strong>


The expression in brackets is true when one range is entirely to the left or right of the other. This condition is pretty easy to visualize. The ranges overlap if and only if it is false.
