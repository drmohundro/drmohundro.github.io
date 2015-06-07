---
layout: post
title: "A simple lesson using type converters"
date: 2007/08/22
category: blog
---

I found myself writing the following code this evening:

{% highlight csharp %}
public T GetItem<T>(string name)
{
  string result = node.SelectSingleNode(name).InnerText.Trim();

  return (T)GetConverter(typeof(T)).ConvertFromString(result);
}

private TypeConverter GetConverter(Type objectType)
{
  if (objectType.Equals(typeof(int)))
    return new Int32Converter();
  else if (objectType.Equals(typeof(bool)))
    return new BooleanConverter();
  else if (objectType.Equals(typeof(string)))
    return new StringConverter();
  else
    throw new ArgumentException("Does not support casting to " + objectType.Name);
}
{% endhighlight %}

Don't ever write code like this. [Read the documentation](http://msdn2.microsoft.com/en-us/library/system.componentmodel.booleanconverter.aspx) which explicitly says that "you should never create an instance of a BooleanConverter". If you follow their advice, your code will become much cleaner. Like so:

{% highlight csharp %}
public T GetItem<T>(string name)
{
  string result = node.SelectSingleNode(name).InnerText.Trim();
  return (T)TypeDescriptor.GetConverter(typeof(T)).ConvertFromString(result);
}
{% endhighlight %}

