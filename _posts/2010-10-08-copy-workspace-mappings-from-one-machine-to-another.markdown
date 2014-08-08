---
author: marknadig
comments: true
date: 2010-10-08 21:02:17+00:00
layout: post
slug: copy-workspace-mappings-from-one-machine-to-another
title: Copy workspace mappings from one machine to another
wordpress_id: 54
tags:
- TFS
---

From a command prompt:

**tf workspace /s:http://tfs:8080 WorkspaceName;DOMAIN\YourUserName**

Then the workspace dialog will pop up and they can select all mappings (Ctrl+A) then copy them (Ctrl+C), then edit mappings in their workspaces by pasting the new mappings over the old ones.

source: [http://blogs.msdn.com/b/mohamedg/archive/2009/04/13/how-to-copy-workspace-mappings.aspx](http://blogs.msdn.com/b/mohamedg/archive/2009/04/13/how-to-copy-workspace-mappings.aspx)
