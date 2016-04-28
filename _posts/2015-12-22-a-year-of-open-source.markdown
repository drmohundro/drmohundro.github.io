---
layout: post
title: "A Year of Open Source"
date: 2015/12/22
category: blog
---

I've been interested in open source software for a while, but it wasn't until last year that I had any success with the software I had released. Back on July 8 of 2014, I pushed the [first commit of SWXMLHash](https://github.com/drmohundro/SWXMLHash/commit/497de2b34cda5114971acf07bbfa179f5991cab7). Incidentally, my first real foray into OSS was also my first real attempt to do any Swift coding.

## Some Stats

First, the GitHub statistics: SWXMLHash has over 350 stars on Github. There have been over 140 commits, 30+ issues, 20+ pull requests, 50+ forks, and 12 contributors.

In addition, it is included in over 600 app installs (per the [statistics on CocoaPods](https://cocoapods.org/pods/SWXMLHash) - I have no idea if this number includes both iOS and Mac apps or not). Needless to say, I *never* imagined that a simple XML parsing library would have that much attention, particularly in the day and age of JSON.

The most well-known app that I'm aware of that is using SWXMLHash is the [Firefox iOS application](https://github.com/mozilla/firefox-ios). [See their Cartfile](https://github.com/mozilla/firefox-ios/blob/da61c695d4e72ec620d34b60863cd8d680885e8c/Cartfile#L9) for details.

## Some Thoughts

Given the attention, I've been happy with my ability to continue to be responsive with it. Now granted, most of my attention after the initial release has been to keep up with the movement of Swift and Xcode. Post-release, the only real enhancement I added [was an option to use lazy-loading for XML](https://github.com/drmohundro/SWXMLHash/pull/17) which has the potential to drastically increase the speed as well as decrease the memory usage of the library.

What I have seen is that being friendly is a necessity. Many people are apprehensive about submitting code (including me). I [tweeted last year](https://twitter.com/drmohundro/status/496485082564411393) that "almost every time I open a new pull request and don't know the people involved, I feel like I need to ask permission to change their code." I often still feel that way. Being on the *receiving* side of pull requests, though, let me tell you that I find them very welcome. Not only does it communicate that other people are willing to help, it also tells me that my library is useful enough to them that they want to improve it.

The *only* difficulty I've had with my brief open source experience is that I do have a few "help me code" questions. I suspect this is because 1) there are a lot of iOS developers and 2) iOS development is easy to get involved in (buy a Mac and download Xcode from the app store). I still have found it rewarding to help out in these situations, though.

## Some Takeaways

If you've been holding off on submitting any code to an open source library, don't stress! I'd recommend finding a library that you respect or use often and see if there are any issues with labels like "help wanted" or "up for grabs". These labels often indicate that someone is *looking* for help. Clone the source down and check it out.

I *would* recommend reading up and learning more about git. Some open source libraries are more picky about [commit message formats](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html). Create a Github repository and play with pull requests - see how commits pushed to a branch show up on the pull request. Add some comments to it and see how you can tie issues to it. It might even be worthwhile to read up on rebasing if the project you're interested in feels strongly about cleaner commit history. I'd also see if the library has any [contributing docs](https://github.com/rails/rails/blob/master/CONTRIBUTING.md).

Feel free to shoot any questions or suggestions regarding your experiences with open source!
