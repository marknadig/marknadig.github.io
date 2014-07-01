---
author: marknadig
comments: true
date: 2012-11-03 15:07:43+00:00
layout: post
slug: ubuntu-getting-up-and-running
title: Ubuntu - getting up and running
wordpress_id: 260
categories:
- ubuntu
---

### **Chrome**


Downloaded and installed chrome from google and got:

    
    Lintian check results for /home/mark/Downloads/google-chrome-stable_current_i386.deb: E: google-chrome-stable: file-in-etc-not-marked-as-conffile etc/cron.daily/google-chrome


The root problem was described here [http://code.google.com/p/chromium/issue/d](http://code.google.com/p/chromium/issues/detail?id=73422)[s](http://code.google.com/p/chromium/issues/detail?id=73422)[etail?id=73422](http://code.google.com/p/chromium/issues/detail?id=73422), which basically describes there were dependencies that weren't being auto installed. So, running package installer from terminal show which packages are missing and then you can just install them.

    
    $ sudo dpkg -i google-chrome-stable_current_i386.deb
    $ sudo apt-get install libcurl3   # or whatever is missing
    $ sudo apt-get -f install  # will resume installing the rest




### **Dropbox**


**** Initially I tried to install from ubuntu software center, but after I launched it said “dropbox is in the wrong folder”. So, downloaded from [www.dropbox.com](http://www.dropbox.com/) and installed .deb from there.


### **Passwordsafe**


**** I installed from [http://sourceforge.net/projects/passwordsafe/](http://sourceforge.net/projects/passwordsafe/) and ran into a similar problem as chrome:

    
    Lintian check results for /home/mark/Downloads/passwordsafe-ubuntu-0.8BETA.i686.deb:
    E: passwordsafe: control-file-has-bad-permissions postinst 0775 != 0755
    E: passwordsafe: control-file-has-bad-permissions prerm 0775 != 0755
    E: passwordsafe: dir-or-file-in-tmp tmp/pwsafe.desktop
    E: passwordsafe: dir-or-file-in-tmp tmp/pwsafe.png



    
    So, running from terminal revealed what dependencies were missing and installed from thre.




### **Skype**


Initially I downloaded from ubuntu software center, but it wouldn't install. So I downloaded directly from skype.com and it worked, but it's a bit clunky.


### **WebStorm/RubyMine**


There's no real installer for RM/WS - just download a zip. What is missing is the JDK which no longer is included in ubuntu by default. Thankfully found thise posts [http://www.webupd8.org/2011/09/how-to-install-oracle-java-7-jdk-in.html](http://www.webupd8.org/2011/09/how-to-install-oracle-java-7-jdk-in.html) and am golden.


### git


from terminal

    
    sudo apt-get install git


[
](http://mattslay.com/installing-rubymine-4-on-ubuntu-12-04/)
