---
layout: post  
title: 'Live Mesh at Day of .Net'
---
I spent the morning at the Ann Arbor [Day of .Net](http://www.dayofdotnet.org/) (AADoDN). What are Day of .Net events you ask?

> The Day of .NET's are a one-day conference on all things .NET organized by developers for developers. These events are usually offered at no cost to anyone interested in .NET development. 
> 
> These conferences are ran by local user groups and rely on volunteers to make them happen. 

If you’ve ever been to a Professional Developer’s Conference the format is similar. Excellent, detailed, deep-dive presentations given by real-world developers on topics they are passionate about. It’s a lot of fun and the information content is dense and rich. It’s a bit like drinking from a fire hose.

![](/cdn/images/blog/LiveMeshatAADoDN_855C/image.png)

Live Mesh is a product/online service from Microsoft that synchronizes all your PC’s (and soon Mac’s) and other digital devices. When I first saw this I was mostly unimpressed since I use [Mozy](http://mozy.com/) for backups and [SkyDrive](http://skydrive.live.com/) (and others) for file sharing. It didn’t really register.

Well, like so many things in life, I totally missed the point. Jeff Blankenburg’s talk yesterday enlightened me as to the coolness that is Live Mesh.

First some quick facts:

  * Live Mesh is a Tech Preview (as in beta, as in not released yet) 
  * Live Mesh is about synchronization and not backup 
  * Even though it’s not about backup you can use it that way if you understand/accept the limitations 
  * You get 5GB of storage 
  * It syncs PDA’s as well as PC’s (and Mac’s soon) 
  * It has a built-in remote desktop 
  * It’s free! 

Now all that’s well and good but what I failed to grasp when I first looked at it was the synchronization happens in almost real-time. Save a file and within seconds it’s on the “Mesh” and syncing with your other devices (provided they’re on online). Add a contact on your PC and within seconds it can be syncing with your PDA. No more periodically plugging your PDA into your laptop(s) to keep everything in sync.

And like any good online service, you can share your folders with others, not just devices. This opens the door to all sorts of collaboration scenarios. However, as Jeff pointed out, the current release gives all participants full ownership/rights to the folder. A future version is promised to remedy that limitation.

I have not used the remote desktop feature yet but Jeff says it punches through most firewalls easily. My company’s IT has already blocked Live Mesh so I won’t be able to verify this claim. If it works as good as [LogMeIn](https://secure.logmein.com/home.asp?lang=en) (my all time favorite) then I’m all in.

Jeff also hinted that there will be **significant** announcements at the PDC next week as to new features and services available from Live Mesh.

Last night I fired up Live Mesh for a second time and with my new found knowledge, I’ve found most of what Jeff has reported is true. It easily synced about 2GB of data on my laptop last night. This morning I made some changes to some documents, and sure enough, within a few seconds the Mesh log showed some new updates had arrived. Pretty cool. I’m going to set up my wife’s computer later today to see how multiple device syncing works.

There were lots of questions yesterday. Here are a few I remembered:

**What happens if you go over the 5GB limit?**

The 5GB is really an online storage limit. Mesh is really about getting to your documents anytime, anywhere from your devices. The 5GB can be thought of as buffer or holding area. If you exceed this “buffer” then Live Mesh simply goes into “peer to peer mode” to sync devices.

**Does it keep revisions of files?**

No. That’s why I mentioned earlier that you can use it as a backup solution only if you accept it’s limitations. Backup services like Mozy keep revisions which allow you to “undo” your saves. Mesh does not do this nor is it designed to.

**Can I share applications?**

Likely. There “might” be an announcement about this next week at the PDC. Frankly, it’s not much of a stretch (even for me) to see where this is going. The idea of licensing an application once and using it anywhere is very appealing. It’s why I only buy music from Amazon (Amazon downloads are DRM free).

**Is there an SDK available for writing applications?**

There “might” be an announcement about this at the PDC next week.

As I begin to grok Mesh I’m understanding there’s more to it than just file backup and syncing. It’s definitely going to be fire hose time at the PDC next week. Jeff has an active blog at [http://jeffblankenburg.com](http://jeffblankenburg.com) and a Silverlight version at [http://jeffblankenburg.info](http://jeffblankenburg.info). I could not access the Silverlight site version of his site with the recently installed Silverlight 2 RTW.
