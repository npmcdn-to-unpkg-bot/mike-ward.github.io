---
layout: post  
title: 'Writing for Deployment'
---
One of the things I try to think about when coding is what I call "Writing for Deployment". Too often I have encountered software that is difficult to install and configure. Most of the time, but not always, these are legacy systems that have matured over a long period of time. During this long gestation, changes are added that in and of themselves are seemingly simple, but taken in their aggregate cause headaches for customers and field technicians alike. Here are some of things I do to try to minimize deployment issues (many of these are Windows specific). 

**Deploy as a single binary**: This is the one I get beat up on the most, so I'll lead with it. If you can deploy your code as a single DLL or EXE, do it. I get a lot of push back on this one and I'm always left a bit puzzled. The arguments are usually along the line of it's easier to patch or it will take too long to build. The patching argument sounds fine in theory, but in practice I have found that the the entire product is updated because of version numbers and labeling requirements. Also, most code is not as modular as it advertises. Invariably, a change in one place requires rebuilding all or most of the modules in the project. Taking too long to build is perhaps a better argument but my experience doesn't support it here either. A single target is easier to build, debug and deploy. In cases where you can't deploy as a single binary, then deploy with as few as you can get away it. A single DLL or EXE is ideal because its just harder for someone to mess it up. Either it's the old one or the new one. Not much confusion there.

**No registry:** The registry seems so handy and innocent, but don't go there. Registry settings cause all sorts of headaches. They require special privileges to modify, they're global which inhibits side by side deployment, they're difficult to undo usually requiring a sophisticated uninstall program (and again, special privileges). 

**Configuration files are optional:** This one drives me up the wall. Move a configuration file and the program goes south. If there's no configuration file, do the nice thing and fall back to some reasonable defaults. Worse still is the configuration file that points to other configuration files.

**Allow side by side execution:** Users have good reasons to sometimes want multiple copies of your program on the same system. Also, allow older and newer versions to run at the same time.

**Test your uninstall:** It's really annoying when I uninstall a program only to find file associations and menu items left over.

**Think USB:** Strive to make your program run without an installer. Again, a single .EXE makes this easier. Also consider using Isolated Storage (.NET) if you have to store configuration information.

**Ask few questions:** If you write an installer, you should ask as few questions as necessary. I hate having to make decisions about obscure program options I don't know anything about.

**Always run:** Short of a nuclear strike, your program should run. If necessary items are missing, it should still run and degrade gracefully.

**Embed resources:** This dovetails with the single binary. In .NET it's easy to embed resources. I really don't need to know your program has 57 different icons spread across 10 directories.

**Silent install:** Installers should allow silent operation with options specified on the command line.

**Set security:** This is mostly .NET again. Take a few minutes and add security descriptors to your assembly. Administrators will cheer you.

**Use limited accounts for development:** This helps you find permission issues with your program early on. You can always "Run as" to run installers. 

**You're a guest on the system, behave appropriately:** Hey, it's not your computer. Be nice.
