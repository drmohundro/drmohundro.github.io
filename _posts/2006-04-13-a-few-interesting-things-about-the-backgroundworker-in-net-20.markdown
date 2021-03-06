---
layout: post
title: "A few interesting things about the BackgroundWorker in .NET 2.0"
date: 2006/04/13
category: blog
---

I stumbled across this [post](http://pluralsight.com/blogs/mike/archive/2005/10/21/15783.aspx) by Mike Woodring today. Apparently, the UserState property from the BackgroundWorker isn't accessible from the RunWorkerCompleted event. What in the world???

Anyway, I wasn't actually looking for information on the UserState property -- I was trying to find some information on the Error property off of RunWorkerCompletedEventArgs. It gets populated when an exception is thrown in your background thread. The weird thing is, I couldn't get my code to fall in there. The debugger kept popping up on the line where I was actually throwing the exception. Believe it or not, but that is actually the intended behavior... IF you're running in the debugger. Check out this [post](http://forums.microsoft.com/MSDN/ShowPost.aspx?PostID=206957&SiteID=1) on the MSDN forums. If you're running standalone, then the Error property will be set as expected and you can check it. I wonder if you can continue on the exception and get to the RunWorkerCompleted event. I'll have to try that.

One last potential gotcha involving using the Error property: make sure it is the FIRST thing you check in your RunWorkerCompleted event handler. See this [post](http://forums.microsoft.com/MSDN/ShowPost.aspx?PostID=302191&SiteID=1) on the MSDN forums for details there. According to Mike Woodring's post referenced above, if you access the Result property off of the RunWorkerCompletedEventArgs parameter and the Error property is populated or the Cancelled property is true, you'll get an invalid operation exception.

So now you know... and knowing is half the battle!

