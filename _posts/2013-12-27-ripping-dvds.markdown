---
author: marknadig
comments: true
date: 2013-12-27 16:59:42+00:00
layout: post
slug: ripping-dvds
title: Ripping DVDs
wordpress_id: 663
categories:
- DVD
---

Over Christmas break I wanted to rip some DVDs I received so I can stream to my xbox. Previously I would use DVDFab to decrypt DVDs to VOB and then Auto Gordian Knot (AutoGK) to transcode the VOB to AVI. The entire process took quite a while for each DVD. To mitigate the time involved, I would decode all the VOBs and then queue up many transcode jobs w/ AutoGK and let it run overnight. Nice, but slow.

I found a better way. I used [MakeMKV](http://makemkv.com/), which support both windows and mac, to decode and create a MKV from a DVD. This took maybe 10 minutes for a DVD. Xbox/windows media center won't play MKV directly, so I still needed to transcode. Here I used ffmpeg to transcode video from mpeg2 to mpeg4 and audio from either pcm or aac to mp3 with:

`ffmpeg -i "input.mkv" -f avi -c:v mpeg4 -b:v 4000k -c:a libmp3lame -b:a 320k "converted.avi"`

or in a batch (windows)

`for %a in (*.mkv) do ffmpeg -i "%~na.mkv" -f avi -c:v mpeg4 -b:v 4000k -c:a libmp3lame -b:a 320k "%~na.avi"`

Note: To just change container; e.g. mkv to mp4:

`ffmpeg -i "input.mkv" -vcodec copy -acodec copy "output.mp4"`

Note: Some posts indicate using "-absf aac_adtstoasc" also.

Found from [http://superuser.com/questions/227338/how-to-convert-an-mkv-to-avi-with-minimal-loss/467980#467980](http://superuser.com/questions/227338/how-to-convert-an-mkv-to-avi-with-minimal-loss/467980#467980)
