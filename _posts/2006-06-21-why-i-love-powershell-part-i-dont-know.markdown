---
layout: post
title: "Why I love PowerShell part... I don't know..."
date: 2006/06/21
category: blog
---

Check out this snippet:

{% highlight powershell %}
dir -recurse -include tempproj.proj | foreach { rm $_ }
{% endhighlight %}

Awesome!

Recursively removing files!

