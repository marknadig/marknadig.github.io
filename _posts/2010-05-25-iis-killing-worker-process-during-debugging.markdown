---
author: marknadig
comments: true
date: 2010-05-25 15:13:47+00:00
layout: post
slug: iis-killing-worker-process-during-debugging
title: IIS killing worker process during debugging
wordpress_id: 75
categories:
- Windows 7
---

Windows 7 runs IIS 7.5 and introduces a few changes in debugging. One issue that comes up is if your code hit some breakpoint and if you leave the program in 'break' mode for more than 90 seconds, Visual Studio shows the following message:


[![](/images/2010-05-25-iis-killing-worker-process-during-debugging1.png)](/images/2010-05-25-iis-killing-worker-process-during-debugging1.png)
		

As help indicates you can either set Ping Enabled=False or increase the Ping Maximum Response Time from the default of 90s:


  1. Open **Internet Information Services (IIS) Manager**.


  2. From the server tree (the item with the name as the server name), choose **Application Pools**. 


  3. Choose the Application Pool corresponding to your testing IIS website (typically DefaultAppPool) 


  4. Click **Advanced Settings**. 


  5. From the **Process Model** node, change the the **Ping Enabled** property to _False_**
					**or increase **Ping Maximum Response Time (seconds)** (900s = 15 min). 


![](/images/2010-05-25-iis-killing-worker-process-during-debugging2.png)


The server keeps pinging the worker process and waits for a response. When in debugging mode, the worker process is effectively suspended, which results in the ping not being responded.

