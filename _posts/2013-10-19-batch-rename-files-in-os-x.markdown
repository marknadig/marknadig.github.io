---
author: marknadig
comments: true
date: 2013-10-19 16:00:59+00:00
layout: post
slug: batch-rename-files-in-os-x
title: batch rename files in OS X
wordpress_id: 642
categories:
- OS X
---

I had ripped a bunch of MP3s in iTunes for my daughter only to find it took too much space for her player. I transcoded the MP3s to 96kbps in iTunes which resulted in two files:
`original.mp3
original 1.mp3`

I now wanted to delete all the originals, and rename the sequenced versions by dropping the numeric sequence:

`
# copy off the keepers
mv *1.mp3 tmp
rm *.mp3
mv tmp/*.mp3 .
rm tmp
# rename, removing ' 1' sufffix
for n in *.mp3
do
mv "$n" "$(echo $n | sed -e 's/ 1\.mp3/.mp3/')"
done`
