---
layout: post
title: "Simple tip to change your PowerShell Script Execution Policy in Vista"
date: 2006/09/08
category: blog
---

Having trouble changing your PowerShell Script Execution Policy in Vista because of access problems? This whole limited user thing will take some time to get used to, but it certainly is a good idea for security. What I did to fix this problem was I ran the command prompt as an admin. If you go under your start menu and accessories, you'll see a link to the command prompt. If you right click on it, you'll see an option to run as administrator. Here's a screenshot:

![Run as administrator](/images/blog/2006-09-07-cmd-admin.png)

Once you do that, you'll be able to start up Powershell and then you'll have authority to change the execution policy. I've typically been setting mine to RemoteSigned (`Set-ExecutionPolicy RemoteSigned`).

Unrelated to Powershell, but wow will I need more memory if I want to run Vista! I barely have any programs open and my pagefile is getting hit like crazy! I'm probably averaging a gig of memory usage... with only one program open!


