---
author: marknadig
comments: true
date: 2012-11-29 21:49:13+00:00
layout: post
slug: ruby-1-9-and-ssl-error
title: Ruby 1.9 and SSL error
wordpress_id: 293
categories:
- Ruby on Rails
---

Got this error today w/ my rails app locally hitting S3

    
    SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed (OpenSSL::SSL::SSLError)


Thankfully found a great explanation and discussion on this [blog](http://martinottenwaelter.fr/2010/12/ruby19-and-the-ssl-error/) and ultimately Tom Gallagher's comment on how to fix this w/ homebrew:

    
    rvm pkg install openssl
    rvm install 1.9.3 –with-openssl-dir=$rvm_path/usr
    cd $rvm_path/usr/ssl
    curl -O <a href="http://curl.haxx.se/ca/cacert.pem" rel="nofollow">http://curl.haxx.se/ca/cacert.pem</a>
    mv cacert.pem cert.pem
