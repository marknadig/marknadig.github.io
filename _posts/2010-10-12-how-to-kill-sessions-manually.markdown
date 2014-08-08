---
author: marknadig
comments: true
date: 2010-10-12 22:48:25+00:00
layout: post
slug: how-to-kill-sessions-manually
title: How to kill sessions manually
wordpress_id: 48
tags:
- Oracle
---

Query to get SID and SERIAL#:
SELECT sid, serial#, username FROM v$session  

<blockquote>

> 
> Optionally filter WHERE username=....
> 
> </blockquote>

Once you found the one to kill:
ALTER SYSTEM KILL SESSION '_[sid]_,_[serial#]_'

Generate kills for all connections for a given user: SELECT 'alter system kill session ''' || sid || ',' || serial# || ''';' FROM v$session WHERE Username = 'MAKODEMO';

