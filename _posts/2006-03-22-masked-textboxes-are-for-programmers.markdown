---
layout: post
title: "Masked textboxes are for programmers..."
date: 2006/03/22
category: blog
---

At work, we're slowly moving from a classic ASP Intranet environment to a smart client environment. It has been very interesting watching (and being a part of) this movement. The typical intranet application is usually a form that consists of grabbing user input and doing something with it. Validating that user input can be a major headache. Typically, good applications would have both client-side (to improve usability and let users know about invalid data early on) and server-side (to ensure that nothing weird happened and to guarantee that the data is valid).

Where am I going with this? Well, I've seen more and more of my coworkers jumping at the chance to use masked textboxes. And you know why? I think it is because masked textboxes offer "free" validation. If you're unfamiliar with masked textboxes, you provide a mask (i.e. (999) 000-0000 for phone numbers) and the textbox will only accept input that matches the mask. It is basically a guarantee that the data from the textbox will be in the format you specify. If you only want 5 numbers, a dash, and 4 numbers (standard U.S. zip code), that's what you'll get. The problem is that it isn't particularly user friendly. There isn't any notification to the user when they type something invalid that it didn't take their input. It just sits there. It also lets them put their cursor in the middle of the mask, so they can start typing anywhere.

I really think that Jeff Atwood hit the nail on the head when he said that we should "we let the user enter the number however they like, and accept lots of formats" (see his post [here](http://www.codinghorror.com/blog/archives/000532.html)). I think that the masked textbox idea could work if the mask it displays were gray and showed the user an example of what the input might look like; however, I don't think it should hinder a user's input. As soon as the user focuses, it could clear so they could type freely. Outlook has a similar feature in the search contact box at the top of the window (see image below).

![Outlook screenshot](/images/blog/2006-03-22-OutlookFindContact.png)

I'd be curious if anyone has any really successful uses of masked textboxes. And I'm talking about cases where you know the user likes the functionality, not where you like it because it saved you a little bit of validation time :)

