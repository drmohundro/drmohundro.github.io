---
layout: post
title: "System.Windows.Forms.WebBrowser and Selenium"
date: 2007/08/07
category: blog
---

I work with the WebBrowser control that was introduced in .NET 2.0 (as well as the ActiveX browser it is based on) a lot at work. As a result, I've come to learn a lot about some of the various intricacies that Internet Explorer has as well as the browser control in general. 

Because we're not running some of our web pages in Internet Explorer but in a custom web browser, unit testing frameworks like Watir and Watin won't work for us. They make use of the Internet Explorer COM application. Unless we want to fork one of those frameworks as well as provide an automation interface into our custom browser, I don't see either of those frameworks working for us. 

However, [Selenium](https://selenium.dev/) will work fine! 

Selenium runs *in the browser*! 

![Selenium in the Browser](/images/blog/WindowsLiveWriter/System.Windows.For.WebBrowserandSelenium_C2DD/image.png)

That's a picture of a little WinForms application I put together that is hosting the WebBrowser control. As you can see, all but one of shipped Selenium tests passed (the only one that failed had to do with opening an XHTML page).

Looks pretty good to me!

