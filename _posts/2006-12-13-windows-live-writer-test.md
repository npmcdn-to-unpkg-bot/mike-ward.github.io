---
layout: post  
title: 'Windows Live Writer Test'
---
This entry tests [Microsoft's Windows Live Writer](http://ideas.live.com/programpage.aspx?versionId=4372c8c2-b76f-4d44-aea1-9835b61d8dc1) (WLW) with [Bloget](/bloget). Looks like things are working well. One major issue was getting categories to work. After hours of searching, I found that WLW wants a title and category-id included in the `struct` of the metaWeblog.getCategories response. If you examine the RFC for the [MetaWebLog Api](http://www.xmlrpc.com/metaWeblogApi) you'll find no such parameters. Why can't we adhere to the standard? The standard is as the standard does I suppose.

As for the WLW, it's pretty darn nice. It feels better than any of the other off-line editors I've used to date. The interface just feels right for whatever reason. There are a few bugs but then again, it is beta software. Also, no spell checking as you type. Nice going Microsoft.
