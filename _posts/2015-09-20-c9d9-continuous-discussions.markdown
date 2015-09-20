---
layout: post
title: "#c9d9 Continuous Discussions"
date: 2015/09/20
category: blog
---

About a month ago, I was invited to participate in an online panel discussion on a [Continuous Discussions (#c9d9) episode](http://electric-cloud.com/lp/continuous-discussions/), which was organized by [Electric Cloud](http://electric-cloud.com/powering-continuous-delivery/). It was set up over Google Hangouts and everyone had some really great thoughts. If you've ever participated in a well-organized open spaces session or sat in on a speakers panel at a conference, it felt a little bit like that. I'd encourage you to check it out.

You can see a recording of the panel here:

<iframe width="560" height="315" src="https://www.youtube.com/embed/HkLuAOXxuLs" frameborder="0" allowfullscreen></iframe>

I've included a brief overview of my thoughts and comments from the panel below.

## Culture and team structure

> I think ownership is the main thing.

I shared an anecdote about how, at one of my recent jobs, we were having a stretch of bad production issues that were all the result of deployments gone wrong. To provide some additional background for this team, both the IT and development team received downtime text alerts. In other words, if the system went down at 3AM, each and every one of us would get woken up with a text alert. Before you have a heart attack, I'm not recommending every team do this; however, what I observed is that we all participated in owning the problem and solving it. The IT and development teams came together and we completely reworked our deployment process. The end result? We had over 2 years with zero downtime as a result of deployments.

In addition, we included our support team in discussions about deployments. We began introducing automated communication ( usually, release notes about the deployment built from our commits) which ensured that they would be able to accurately communicate with our end-users about what's going on.

## Communication and hand-offs

The primary thing I attempted to communicate during this section of our discussion was transparency, whether it was in stand ups, sprint reviews, or even commit messages. Instead of developers feeling like they have to speak up about everything, the goal is for them to feel like they have a voice. Most developers I've worked with want the business to accurately understand the amount of work involved or how complex a task is. The more transparency in communication there is, the more teams can trust that they're being accurately represented.

## Automation

> We were PCI compliant, so there had to be some sort of manager sign-off for everything that went into production. So that provided an excuse for not automating – the team was saying, 'we can't automate releases because we need a sign-off'. So I said, automate as far as you can – automate all the way up to the staging environment. So there is, ideally, a compressed build of everything that will go to production, sitting on staging, that has all the monitoring and smoke tests on it. We're so confident about it, that maybe the person who approves it can just click a button and then it goes out to production.

The main thing I focused on while speaking on automation was how much it can help, even in an environment that deals with PCI, HIPAA or SOX. I shared a story about how a manager didn't believe that my team could be both PCI level 1 compliant *and* do multiple releases during a day - they had never seen it done. When I showed him our audit log of deployments along with the commit ranges that made up each deployment *and* the developer and managers that had signed off, he was convinced!

## Versioning and sharing binaries, environments and processes

> Release as much as you can, but be aware of the things that you can't.

Regarding versioning environments, I shared how we weren't able to completely automate our entire environment - in our case, our database required some manual work. For example, we didn't have database migrations or even a great story for source control for our database. Because we recognized this, we instead treated our database like an API - in other words, _no breaking changes_!

An honest and accurate understanding of where we stood helped us continue to iterate and not end up in analysis paralysis trying to end up with the perfect environment and architecture.

## In closing

I really enjoyed the discussion - the other participants all had some great observations as well. Let me know your thoughts!
