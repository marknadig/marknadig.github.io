---
author: marknadig
comments: true
date: 2012-08-29 23:02:07+00:00
layout: post
slug: going-from-macports-to-homebrew
title: Going from MacPorts to Homebrew
wordpress_id: 232
categories:
- OS X
---

Many blogs out there outline the process (1), (2), (3). Having upgraded to Ruby 1.9.3 and running into a segfault issue resolved by brew ([https://github.com/capistrano/capistrano/issues/250](https://github.com/capistrano/capistrano/issues/250)) ([http://bugs.ruby-lang.org/issues/5559](http://bugs.ruby-lang.org/issues/5559)), I thought it was time. So, I'm on the bandwagon.

First, following the [official instructions](http://guide.macports.org/chunked/installing.macports.uninstalling.html), remove macports. **Note**: Macports installed mysql puts your db in /opt/local/var/db so back them up if you care. Also, check the official site for updates to these steps.

    
    # Remove all installed ports
    sudo port -fp uninstall installed
    
    # cleanup remnants
    sudo rm -rf \
    /opt/local \
    /Applications/DarwinPorts \
    /Applications/MacPorts \
    /Library/LaunchDaemons/org.macports.* \
    /Library/Receipts/DarwinPorts*.pkg \
    /Library/Receipts/MacPorts*.pkg \
    /Library/StartupItems/DarwinPortsStartup \
    /Library/Tcl/darwinports1.0 \
    /Library/Tcl/macports1.0 \
    ~/.macports


Now install Homebrew as outlined on the [official site](http://mxcl.github.com/homebrew/). Note: Check the website before running this script as it may change.

    
    <code id="selectable">ruby <(curl -fsSkL raw.github.com/mxcl/homebrew/go)</code>


Then follow the prompts.

Now, ready to install the rest of the stuff.

    
    brew install imagemagick


I did opt to install mysql directly from oracle: [http://www.mysql.com/downloads/mysql/](http://www.mysql.com/downloads/mysql/) following (4).

In order to rebuild my rvm gemsets, I could have done it the 'easy way', but I preferred slash and burn:

    
    # Completely remove RVM
    rvm implode
    # re-install rvm
    bash < <(curl -s https://raw.github.com/wayneeseguin/rvm/master/binscripts/rvm-installer) 
    # reinstall ruby
    rvm install ruby1.9.2-p290


Here, rvm informed me that Ruby needs gcc to compile and xcode 4.4.1 doens't come with it and to do the following in another terminal window:

    
    brew update
    brew tap homebrew/dupes
    brew install autoconf automake apple-gcc42
    rvm pkg install openssl


Now it is ready to continue to install ruby

    
    Refs:


(1) [http://orange-pants.com/databases/homebrew-on-mac-osx-lion/](http://orange-pants.com/databases/homebrew-on-mac-osx-lion/)

(2) [http://bitboxer.de/2010/06/03/moving-from-macports-to-homebrew/](http://bitboxer.de/2010/06/03/moving-from-macports-to-homebrew/)

(3) [http://osxastrotricks.wordpress.com/2012/03/19/switch-from-macports-to-homebrew/](http://osxastrotricks.wordpress.com/2012/03/19/switch-from-macports-to-homebrew/)

(4) [http://astonj.com/tech/how-to-install-mysql-on-lion-mac-os-x/](http://astonj.com/tech/how-to-install-mysql-on-lion-mac-os-x/)
