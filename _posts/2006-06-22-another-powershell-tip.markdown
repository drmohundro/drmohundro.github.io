---
layout: post
title: "Another PowerShell tip..."
date: 2006/06/22
category: blog
---

I can't help myself, PowerShell is great and I keep finding useful things to do with it. Most of what I've been finding is easily accomplished in other ways, but this just goes to show the power available straight from the PowerShell command prompt.

What if you want to know the full path to all of the solutions in a sub-directory?

You could try this:

{% highlight powershell %}
dir -recurse -include *.sln . | foreach { $_.FullName }
{% endhighlight %}
    
This builds on my [post](/blog/2006/06/21/why-i-love-powershell-part-i-dont-know/) from yesterday.

