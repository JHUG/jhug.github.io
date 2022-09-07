---
title: Java 17 Innovations Developer Live
date: 2021-09-19T10:00:00+03:00
author: Ioanna Katsanou
author linkedin: https://www.linkedin.com/in/ioannakatsanou/
author twitter: https://twitter.com/ioannakatsanou
layout: post
categories:
  - java
tags:
  - community
---

>A post by JHUG member [Ioanna Katsanou](https://www.linkedin.com/in/ioannakatsanou/) who attended the Java Innovations event for the release of Java 17 and sent us her impressions. Enjoy!

I attended recently, on September 16th, the Java Innovations all day event concerning Oracle’s new java 17 version and would like to share my experience about it.

In the beginning a welcome panel featured a brief introduction to the new JDK, and presented a small preview to their plans for the future.
There was also an entertaining poll featuring questions about  Duke -the famous Java mascot- and who is the Java Architect. (FYI Duke was created by Joe Palrang and Mark Reinhold is the Java Architect)

The most interesting ongoing projects that caught my attention were:
* Project Panama: A project for improving and enriching the connections between the Java non-Java APIs, (for example C language interfaces).
* Project Amber: This project aims to enhance the Java SDK with new features and improve the Java programming language.
* Project Lanai: A new Java2D graphics pipeline for macOS.

The JMS (Java Management Service) - not to be confused with Java Messaging Service with the same acronyms, was also highlighted. This is a new Oracle Cloud Infrastructure Service that aims to help manage all Java applications deployed on the cloud. It is included with Java SE Subscriptions and Java SE Desktop Subscription and is free in the OCI (it does not include cost of monitoring data).
After these two sessions, I was really excited about the next session with Mala Gupta, since she is one of my favorite developers, as well as a Java Champion!

The session was very pleasant with a lot of fun surprises. She presented the new pattern matching for switch (this is still a preview feature of the Java language but it is going to be included in the official version soon). She also made apt code comparisons with real life scenarios. It is not surprising that her nickname is “Switchy Gupta”. 

## Hands-On Labs

Next in row, were the two hands-on labs.

The first lab was presented by David Delabassée. The goal of the lab was to explore all the new Java SDK 17 features on the Cloud. Basically you have to set up your OCI Account and environment first. Then by connecting through SSH to the cloud instance, the lab provides an initial introduction to Helidon and a beginner exposure to open-source Java-based collection of libraries that one can use to develop lightweight Microservices. 
Next we downloaded a ready project from Github and experimented through some key Java 17 features such as sealed classes, records, pattern matching etc.! 
I also had to write Java code in the command line using Vim or Nano for the lab purposes and as I am used to using an IDE, this alone was quite a challenge for me! I really found this lab interesting
In case anyone wants to get their hands dirty, the link for the lab is:
[David Delabassée Lab](https://delabassee.com/odl2021-lab/)
It will be available for the next 1-2 months at least, so hurry up!


Lastly, the second lab, “Practical Cloud Native Skills for Java Developer” was presented by Joe Greenwald, OCI Learning Solutions Architect and Vasily Strelnikov, Senior Principal OCI Solution Specialist. The purpose of this lab was to build an app, deploy it and run it in Kubernetes.
Unfortunately I was not able to finish this one, as the time was up, but will do in the next days.
You can find instructions to this lab as well as source code in this link:
[Practical Cloud Native Skills for Java Developer](https://github.com/oustudent1/practicalcloudnativejavadev)


## Other Useful Links

* You can find more information about the event as well as a video in the following link:
    https://developer.oracle.com/developer-live/
* https://dev.java/  has replaced the java.sun.com
* https://inside.java/ includes (aggregator of content developed by the java platform group)
    Inside Java Newscast: Time relevant stories about new features, progress of projects
    Sip of Java: Java series of one minute video shorts covering tricks and tips for better development
    Inside Java podcast: Audio series with interviews of the makers of Java
    Jeff café: monthly serving of Java deep diving of one particular JDK Enhancement proposal
* https://blog.jetbrains.com/  Jetbrain’s Blog
* https://delabassee.com/ David Delabassée’s blog