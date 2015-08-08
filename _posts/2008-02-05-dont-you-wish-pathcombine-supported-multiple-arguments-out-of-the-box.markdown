---
layout: post
title: "Don't you wish Path.Combine supported multiple arguments out of the box?"
date: 2008/02/05
category: blog
---

I've found myself wishing that I could pass in more than two arguments to Path.Combine. That is, something like this:

{% highlight csharp %}
Path.Combine(rootPath, someCalculatedPath, someKnownFileName);
{% endhighlight %}

As it is, Path.Combine only accepts two arguments, so I end up with calls that look like this:

{% highlight csharp %}
Path.Combine(Path.Combine(rootPath, comeCalculatedPath), someKnownFileName);
{% endhighlight %}

It seems like a hassle to me. Here is a simple wrapper function (with accompanying test) that will accomplish this:

{% highlight csharp %}
public static class FileUtils
{
    public static string CombinePaths(params string[] paths)
    {
        if (paths.Length == 0) return string.Empty;

        return Path.Combine(paths.First(), CombinePaths(paths.Skip(1).ToArray()));
    }
}

[TestFixture]
public class FileUtilsTests
{
    [Test]
    public void Should_combine_paths_correctly()
    {
        string expected = @"c:\some\path\to\file.txt";

        Assert.AreEqual(expected, FileUtils.CombinePaths("c:\\some", "path\\to", "file.txt"));
    }
}
{% endhighlight %}
