---
layout: post  
title: 'Copy Large Files in Windows'
---
Robocopy (means Robust Copy) is a tool from Microsoft. It is distributed in the Windows 2003 Server Resource kit (along with many other cool tools). Robocopy is faster and much more reliable. It can restart failed transfers and has a rich set of options for mirroring directories, logging and more.

> But there's a problem. The traditional "copy and paste" functionality that is built into Microsoft Windows has limitations. It works well enough for simple tasks (moving a document from one directory to another, and so on), but it lacks the advanced functionality an IT professional needs in the workplace. For example, the copy and paste operation doesn't include any kind of advanced resiliency that would allow it to recover from a brief network disruption. It's also an all-or-nothing proposition, particularly when copying complete directories. Through the UI, you can't choose to copy only those files which are new or have been updated. You either copy individual files, entire directories, or nothing at all.
> 
> Enter Robocopy. This powerful tool, included with the Microsoft Windows Server® 2003 Resource Kit Tools, allows for all of those advanced functions and more. Robocopy enables the more serious file replication tasks that can really simplify your job. The biggest benefit I think you'll find is the ability to create full mirror duplicates of two file structures (including all subdirectories and files, if you choose) without copying any unnecessary files. Only the files that are new or have been updated in the source location will be copied. Robocopy also allows you to preserve all of the associated file information, including date and time stamps, security access control lists (ACLs) and more.

<http://www.microsoft.com/technet/technetmag/issues/2006/11/UtilitySpotlight/>
