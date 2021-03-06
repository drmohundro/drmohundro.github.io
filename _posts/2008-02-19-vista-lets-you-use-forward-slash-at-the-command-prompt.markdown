---
layout: post
title: "Vista lets you use forward slash at the command prompt!"
date: 2008/02/19
category: blog
---

I was just setting at a command prompt in Vista on my laptop and I typed `cd /` out of habit and, to my surprise, it worked! Not only that, but tab completion still behaved as expected! 

I actually have been using the '/' character in PowerShell because it is easier to type than '\' (not as far to reach) and it is the default in *NIX systems as well (i.e. my Ubuntu installation). 

Now granted, I probably shouldn't get used to this in the event that I inadvertently code a '/' character in one of my programs, but then again, I should technically be using the [System.IO.Path.PathSeparator](http://msdn2.microsoft.com/en-us/library/system.io.path.pathseparator.aspx) anyway. 

I get excited about the little things. 

NOTE - this might be the result of Service Pack 1 on Vista also... 

**UPDATE** - I lied. You can type `cd /` and get to the root, but tab completion still completes only for the current directory. In other words, if you're current directory is c:\windows\ and you type `cd /[tab]`, you'll get directories that are in c:\windows. Sorry. My excitement just dropped a little.

