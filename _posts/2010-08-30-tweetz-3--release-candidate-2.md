---
layout: post
title: 'tweetz 3 – Release Candidate #2'
---
I was planning to get RC #2 out a bit earlier but my back has decided to raise hell with me. I’m actually active and healthy but every once and a while I manage to do something that lays me out. However, I’ve managed to stay vertical for the last couple of hours and so I’ve packaged up the latest fixes. Hopefully there are no bad regressions.

  * Ignore bad data. Twitter occasionally sends ill formatted data. [Tweetz](/tweetz) will ignore the bad data instead of crashing
  * Fix the purge old tweets routine to correctly delete the old tweets
  * Fix url parsing to align more closely with how twitter parses urls (exclude trailing ? for instance)
  * Fix misspelling of messages in “Unified” tool tip

Excellent bug hunting guys. Also, the suggestions are great. I’ve added them to the bottom of app.js so you can see which ones I’m aware of.

Available on the [downloads page](/downloads).
