---
layout: post
title: "Simple PowerShell script to generate thumbnails"
date: 2008/10/11
category: blog
---

I was working with a lot of images for a website today and I needed to quickly create thumbnails for each one. I did a quick Google search on PowerShell and creating thumbnails, but I gave up after about a minute... yeah, I probably got impatient, but oh well.

Anyway, here it is:

{% highlight powershell %}
get-childitem *.jpg | foreach {
  $full = [System.Drawing.Image]::FromFile("$(resolve-path $)");
  $thumb = $full.GetThumbnailImage(72, 72, $null, [intptr]::Zero);
  $thumb.Save("$(resolve-path $).thumb.jpg" );
  $full.Dispose();
  $thumb.Dispose();
}
{% endhighlight %}

Obviously, you likely wouldn't hardcode the height and width for the thumbnail, but would probably base it off of the original image (i.e. varying it off of whether the image was wide or tall). But, I didn't need to. That's up to you to figure out :-)

