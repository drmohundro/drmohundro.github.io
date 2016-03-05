---
layout: post
title: "Ping, VPN, etc from Windows XP Mode"
date: 2009/10/22
category: blog
---

I just wanted to share a quick tip on something that had been tripping me up. I've happily been running Windows 7 x64 for around a month now. At work, our VPN hardware doesn't support 64-bit (different topic, don't ask), so I wanted to use the VPN client from within Windows XP Mode. Sounds good, right? 

One problem. The VPN client couldn't see outside networks. In fact, I couldn't even ping. 

![Attempting to ping  from XPM](/images/blog/WindowsLiveWriter/PingVPNetcfromWindowsXPMode_12ADF/image_3.png)

 The default networking adapter seems to be "Shared Networking (NAT)" - just change it to your actual network adapter. 

![Networking adapter settings](/images/blog/WindowsLiveWriter/PingVPNetcfromWindowsXPMode_12ADF/image_6.png)

Success! 

![Successful ping!](/images/blog/WindowsLiveWriter/PingVPNetcfromWindowsXPMode_12ADF/image_9.png)


