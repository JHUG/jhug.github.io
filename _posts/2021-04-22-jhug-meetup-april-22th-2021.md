---
title: JHUG 22-Apr-2021 virtual meetup
date: 2021-04-24T17:00:00+02:00
author: Spiros Anastasopoulos
layout: post
categories:
  - java
tags:
  - community
  - jhug java meetup
---

This Thursday, we had another JHUG virtual meetup. It was the fifth we had during the lockdown and we are very confortable with the format, but we hope to meet and talk face to face very soon. This time around 60 members participated and watched the sessions. As always it was held on google meetup and the details and the link were published on our [slack channel](https://jhug.slack.com).

Now, lets go to the three sessions.

## An unconventional path to innovation

The first talk was by [Babis Makrynikolas](https://www.linkedin.com/in/makrynikolas/) and was about some aspects of the evolution of Amazon from a startup to an internet giant. Babis worked on AWS for some years and has an inside view. The story is well known. Amazon started as an online bookshop and evolved into the biggest online marketplace and one of the biggest cloud providers. Alas, such impressive growth comes at a cost: more people, more teams, more complexity (both business and infrastructure), more coordination, all these cause slowdown. In the Amazon case, the challenge was not only to cope with the complexity but also to use the solutions both as a driving force for innovation and as products for sale. From there started a long journey during which the monolith broke into many microservices and the organization structure was constantly changing accordingly. The driving guidelines were _velocity_, _ownership_ and _failure isolation_. Using this unconventional approach, Amazon succeeded to launch AWS, Amazon marketplace and Amazon prime.

It was a very interesting talk because it was pragmatic, all the use cases were from real life experience. There were many questions during the Q&A sessions, most of them having to do about the application of the Amazon model to smaller organizations. Of course the scale is different and not all of these can be applied, but the driving guidelines of velocity, ownership and failure isolation still apply and can be used to develop a more suitable model for your organization.

This talk was recorded. You can watch the video [here](https://vimeo.com/540659777).

## JVM performance tuning

The second talk was by [Thomas Pliakas](https://www.linkedin.com/in/thomas-pliakas/) and was about JVM tuning. This is a big subject and most of us are unware about most of the capabilities of the JVM. The talk was a guided tour of the JVM tuning flags (__-XX__). During each stop, Thomas explained the flag and for most of them told us war stories that happened to him and how the correct/incorrect application of the flag made a difference. It was an exciting journey around the heap, the GC, the JIT the compiler and all the internals of the JVM. The Q&A session was spent mostly on discussing how modern runtime environments, like docker and kubernetes, affect the tuning strategies.

You can find the slides [here](https://github.com/JHUG/JHUG-General-Resources/blob/master/presentations/2021/04-April/JVMPerformanceTuning.pdf).

## Code reviews

This time, instead of another talk, we decided to have an open discussion about code reviews. The trigger was [this](https://bill.burkecentral.com/2021/03/31/anybody-else-hate-pr-reviews/) blog post by Bill Burke, in which the author argued against code reviews. We discussed it a lot in our slack channel and we decided that we can make a larger conversation, live this time, including more members.

We started with an open agenda. We did not want to repeat best practices or antipatterns. These you can find in many good books and blog posts. We just wanted to tell moral stories including code reviews. The participation was massive and the discussion was very lively. The topics touched covered all the spectrum of the subject. We will cover the full discussion in an upcoming blog post. But until it is published here are some teasers:
- I am the law
- To test or to review? Here is the question
- I feel like an idiot
- We must implement an NLP bot for the code comments
- Captain's log, Stardate 43989.1. I make fixes for the 5th pass of the review. God please make it stop
- Tell the newbie to shutup and listen
- I am here to be useful, not pleasant
- Well, i can't give you a +1, but i know someone who can

## That's all folks

We had a great time with the talks and the vivid Q&A sessions. You are now planning the next meetup which will be virtual again. The details will be published in our [slack](https://jhug.slack.com) channel. You should consider joining our slack because this is our home during the lockdown and we have very interesting discussions and sometimes great flame wars. So, until our next meetup, stay well, take care of yourselves and keep coding.
