---
author: marknadig
comments: true
date: 2010-11-16 22:19:58+00:00
layout: post
slug: build-error-when-publishing-clickonce-after-build-machine-name-changes
title: Build error when publishing clickonce after build machine name changes
wordpress_id: 46
categories:
- VS2010
---

I am testing out building VS2010 projects on a new build VM which is just a copy of the real build vm, the equivelant of "changed the name of my build machine." The Publish Clickonce step failed with 




error MSB3482: An error occurred while signing: Keyset does not exist ...




 




Found this helpful [blog post](http://itdevcorner.blogspot.com/2008/10/keyset-does-not-exist.html) that described how to resolve this, by removing the signing cert from the current user's Certificates->Personal->Certificates:









  1. Open Microsoft Management Console (MMC) by click on Start --> Run  



  2.  Type "MMC.exe" in the text box window (without quotes).


  3.  Click OK. A MMC window will appear.


  4.  Click Console in the new MMC you created, and then click Add/Remove Snap-in.


  5.  In the new window, click Add.


  6.  Highlight the Certificates snap-in, and then click Add.


  7.  Choose the "My User Account" option and click Next.


  8.  Click Close, and then click OK.


  9.   Open the Certificates (Current User) snap-in and navigate to Personal, and then Certificates. You will see the list of  ertificates installed. If you can not find the one that you're looking for then it means it does not exist.


  10.  In the certificate list right click on the certificate you used to sign the manifest and select Delete


  11.  Try to re-publish your .Net project.
  





**Category:** VS2010




**Published:** 11/16/2010 5:03 PM



