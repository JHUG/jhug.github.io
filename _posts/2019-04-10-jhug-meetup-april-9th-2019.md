---
id: 604
title: JHUG meetup April 9th 2019
date: 2019-04-10T23:19:25+02:00
author: Spiros Anastasopoulos
layout: post
guid: http://www.jhug.gr/?p=604
permalink: /archives/604
categories:
  - java
---
The April meetup was sponsored by [Blueground](https://www.theblueground.com/) at the [Impact Hub](https://athens.impacthub.net/) in Psyri, Athens. Apart from leasing the space, Blueground also kindly offered pizzas and beer for all the attendees.

[Kostis Kapelonis](https://www.codepipes.com/) on behalf of JHUG welcomed the participants with an urge. This season JHUG has many proposals from sponsors for meetups but the speakers are limited. He urged people to do talks on all topics regarding java and/or the jvm. JHUG is open to all speakers and topics and most importantly the members of JHUG throughout its lifetime &#8212; it is the oldest Greek meetup founded in 2001 &#8212; have proved that they respect every speaker regardless of the topic, the presentation skills or the content level.

After that [Stratos Pavlakis](https://www.linkedin.com/in/spavlakis/) VP of Engineering at Blueground presented the company, what they do and their engineering culture. It was of great interest when he described that the company started as an operations company but eventually had to evolve into a tech company to handle the increasing scale. Moreover Stratos as a co-organizer of the [GreeceJS](https://greecejs.org/) meetup added some useful thoughts on the topic addressed by Kostis before him.

The meetup then continued as always with two talks and a beer-pizza-networking break.

# Testing Anti-patterns

The first talk was from [Kostis Kapelonis](https://www.codepipes.com/) about software testing anti-patterns. Kostis is a firm believer in that testing done right gives great value to a code base. He has given many presentations on this topic and has written a [book](https://www.manning.com/books/java-testing-with-spock) about it.

Wikipedia defines an [anti-pattern](https://en.wikipedia.org/wiki/Anti-pattern) as _a common response to a recurring problem that is usually ineffective and risks being highly counterproductive_. So, imagine a talk that will tell 100 attendees they do testing wrong, combine it with the lively and provocative presenting style of Kostis and you get the context of the talk.

The talk was a live commentary on a revised edition of a popular [blog post](http://blog.codepipes.com/testing/software-testing-antipatterns.html) by Kostis. After giving an overview of how testing should be done properly he defined and explained the following list of anti-patterns.

  1. Having unit tests without integration tests 
      * Having integration tests without unit tests 
          * Having the wrong kind of tests 
              * Testing the wrong functionality 
                  * Testing internal implementation 
                      * Paying excessive attention to test coverage 
                          * Having flaky or slow tests 
                              * Running tests manually 
                                  * Treating test code as a second class citizen 
                                      * Not converting production bugs to tests 
                                          * Treating TDD as a religion 
                                              * Writing tests without reading documentation first </ol> 
                                                For each one of them, he presented the topic in detail, refuted the arguments that consider it a best practice and explained why it is an anti-pattern. In almost all of the topics there were questions from people who either did not consider it an anti-pattern or were not convinced by Kostis arguments. He answered many questions and eventually the talk went well beyond the time limit so the organizers had to end it.
                                                
                                                The talk was very interesting, easy and enjoyable to follow and thought provoking as expected, and promised, by Kostis. The video will go live soon on our [vimeo channel](https://vimeo.com/javahellenicusergroup) and it is highly recommended. The original blog post is also worth reading. The topic of course is very large and cannot finish in one talk. As a closing note we repeat some of the general advices Kostis gave for proper testing.
                                                
                                                  * Automate, automate, automate 
                                                      * A developer **must** be able to run the whole test suite easily, fast and out of the box for every new code base he is involved. 
                                                          * If tests do not give value to business they are useless even if they are correct and well written. 
                                                              * When in doubt what to test, monitor the state of production </ul> 
                                                                # Introduction to Quarkus
                                                                
                                                                The second talk was about [Quarkus](https://quarkus.io/) a new, very promising framework from Red Hat. The project is very new, released about a month ago so this talk was a JHUG exclusivity. Moreover, the speaker [Georgios Andrianakis](https://twitter.com/geoand86) is a [contributor](https://github.com/quarkusio/quarkus/graphs/contributors) to the project so he has a very good understanding of the design tradeoffs used for quarkus.
                                                                
                                                                He started the talk by setting the context for quarkus, why a new framework was needed and where it stands in the java ecosystem. The problems it addresses are with java in production and mostly with cloud deployments. In such environments characteristics of java like large memory footprints, slow startup times, class loading issues etc are drawbacks and hinter the adoption of java. These are relics of the era where java was used in inhouse clusters and the application servers took full control of the machines. He pointed out that production environments are dynamic in essence, configuration changes, code changes, dependencies changes, and thus a new more flexible way was needed to address these issues.
                                                                
                                                                Then he described Quarkus which is composed of 2 things.
                                                                
                                                                First, a java stack for development that includes well established frameworks like hibernate, Resteasy, eclipse microprofile, netty, kafka, vert.x (enter reactive) and many more are on the way. All these are used by java developers daily and thus if you adopt quarkus you are not forced to learn something new but you can continue to use the things you know and trust.
                                                                
                                                                Second, a runtime environment based on [GraalVM](https://www.graalvm.org/) which powerups your application and gives you smaller memory footprint, very fast startup times, live reloading of code and configuration and if you choose, a native executable. Note that quarkus applications can still run on the JVM if you choose but in this case you lose many of quarkus benefits.
                                                                
                                                                Of course as you understand quarkus is much more than assembling a jar from the above frameworks and running it on GraalVM. It does some hard work both during the build time and during the runtime to ensure that you get the benefits of the platform. During build time it does static code analysis to eliminate dead code, remove unused classes, reduce reflection calls, all of which reduce the memory footprint and fasten application startup. During runtime it does not do aggressive classloading or reflection or dynamic proxied or use agents like JMX as this incurs additional costs that are maybe insignificant for in house deployments but are very expensive for cloud deployments. In a nutshell you must write code the quarkus way. If you use the supported frameworks it is very easy and straightforward. If you don&#8217;t then you must either wait till they are supported or do some good code reviews to make your app quarkus ready.
                                                                
                                                                After the presentation Giorgos gave a live demo that demonstrated build times, startup times, live reloading, native executables and finally support of jpa. It was a very good demo as he was very confident in quarkus and was eager to ask the audience &#8220;what do you want to run next?&#8221;
                                                                
                                                                The Q&A session was about quarkus support, mostly how well it supports spring, a framework that heavily relies on reflection and dynamic proxies and how ready is quarkus for production. Giorgos suggested adoption of quarkus, it is very mature, not production ready yet but it is actively developed and it will be ready for production soon. As for spring support it is improving, some of its parts work fine, but the full framework is not quarkus ready yet.
                                                                
                                                                That was an excellent talk and helped us get a clear view of quarkus beyond the buzzwords. Those that missed it should definitely see the video of the talk when we release it in our [vimeo channel](https://vimeo.com/javahellenicusergroup). Also Giorgos will give another talk for quarkus at the [May Kubernetes meetup](https://www.meetup.com/Athens-Kubernetes-Meetup/events/260480891/)
                                                                
                                                                # Aftermath
                                                                
                                                                Of course besides the talks there was a lot of networking between our members, old and new, and a lot of ideas exchanged. The positive energy that such meetups give to the attendants is enormous.
                                                                
                                                                In this meet up we also made a draw for two IntelliJ licenses a gentle offer of [Jetbrains](https://www.jetbrains.com/) and two tickets for [Voxxed Days Athens](https://voxxeddays.com/athens/) a gentle offer of [SoftConf](http://softconf.eu/). They are both firm supporters of JHUG and we thank them a lot.
                                                                
                                                                # Join JHUG
                                                                
                                                                You can learn news about JHUG, participate and exchange ideas and feedback via our channels:
                                                                
                                                                  * [Slack](https://jhug.slack.com) 
                                                                      * [Twitter](https://twitter.com/jhug) 
                                                                          * [Meetup](https://www.meetup.com/Java-Hellenic-User-Group/) 
                                                                              * [Blog](https://www.jhug.gr) 
                                                                                  * [Vimeo](https://vimeo.com/javahellenicusergroup) </ul> 
                                                                                    News about meetups and other events are published in all these channels but the interesting discussions are on slack. If you are not there, consider joining.
                                                                                    
                                                                                    See you at the next meetup. Until then keep coding.