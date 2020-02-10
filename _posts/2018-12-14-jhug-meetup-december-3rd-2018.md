---
title: JHUG meetup December 3rd 2018
date: 2018-12-14T00:17:03+02:00
author: Markos Fragkakis
layout: post
categories:
  - java
---
The last meetup for 2018 ([meetup.com](https://www.meetup.com/Java-Hellenic-User-Group/events/256415919/)) was sponsored by [Intralot](https://www.intralot.com/) at the [Impact Hub](https://athens.impacthub.net) in Psyri. Apart from leasing the space, Intralot also kindly offered pizzas and beer for all the attendees.

A little more than 100 people attended the meetup, many new faces among them. For those who couldn't attend, we recorded the meetup, so either revisit this post for the videos, or subscribe to our [Vimeo channel](https://vimeo.com/javahellenicusergroup).

The meetup kicked off with Thomas Pliakas, from the JHUG team, who welcomed the attendants on behalf of the group. As Thomas stressed, JHUG exists thanks to people who volunteer to present, so if there is something you like and use and want to share your passion about it, submit a presentation proposal to our [call-for-presentations form](https://docs.google.com/forms/d/e/1FAIpQLSfvWU6zy7bB6stBLL9KN9dOnVFGnQ3ZUy-4JW6pAMYMmQ8GPw/viewform). Also, we have an active Slack channel, check the instructions in the box on the right side of this post to get an invitation.

Afterwards, [Irene Dimou](https://www.linkedin.com/in/irenedimou) took the stage and presented what our host, Intralot, works on, how it is organised, and how much it has grown over the years, now employing over 700 people in Greece and many more worldwide. With the economy crisis still going strong, it is very consoling to see that there are - mostly IT - companies that build expertise and thrive internationally.

## High performance asynchronous transaction orchestration with Java Reactive frameworks

The first presentation was by [Nikos Papadopoulos](https://www.intralot.com/) and Vasilis Petropoulos, both Engineers at Intralot. They started by presenting the special requirements their business brings with it: multitude of clients, large numbers of transactions with spikes in traffic, low response times, regulations for auditing and logging, penalties for mishandled transactions, runtime configurability. A practical aspect that raised some eyebrows was that their traffic may go up several times in a matter of minutes, and then go down again. Their solution needed to scale that fast, and then scale down so as to keep the bill low. They then discussed how the Reactive Manifesto and Microservices with Docker and Kubernetes are a good fit for them.

Nikos and Vasilis then presented the toolset they chose in order to accommodate their needs:

  * Netty: it's significantly more lightweight than Tomcat, event-driven and its thread model is customizable
  * Spring Boot 2 with Spring 5: A mature framework with easy DI configuration and libraries for everything, produces a single containerizable jar file
  * Spring Webflux: Spring's reactive web framework, which can sit on top of Netty, providing mechanisms for back-pressure, filtering, sorting batching etc.
  * Spring Actuator: Spring's library that provides real-time information and metrics on the status of our application
  * Jersey: The popular JAX-RS implementation, which can be used to generate Swagger docs for our APIs
  * jBPM: A business process modelling framework to comceptualize, design and develop service flows

Nikos and Vasilis went on to discuss the challenges they faced implementing their solution, which both technical (i.e. making all the tools work together) and non-technical (introducing a paradigm shift to the asynchronous world for their team). Their implementation, which is in production as you are reading this, met the requirements they had set initially, achieving the elasticity and resilience their clients needs.

A final point we spent some time discussing was the way they are achieving eventual consistency in the distributed world. For each flow, they maintaining a reverse one that reverts it. When kicking off complex operations, they are keeping a log of the list of sub-operations (flows) that need to take place, and if one of them fails, they execute the reverse flows for all executed flows. Although they didn't use the word, this sounds like the Saga pattern.

You can find the presentation [here](https://github.com/JHUG/JHUG-General-Resources/blob/master/presentations/2018/12-December/intralot.pdf)

## Java puzzlers

George Kalfopoulos from Trasys (now part of NRB) prepared 10-minute Java puzzlers session. After some head-scratching and facepalms, the quickest answers won two books we gave away. This small session was so engaging we are very keen to repeating it in the near future.

## JUnit 5

The second talk was by our own [Thomas Pliakas](https://www.linkedin.com/in/thomas-pliakas) on [JUnit 5](https://junit.org/junit5/docs/current/user-guide). Thomas took the risk and did a live-coding session, fortunately everything worked out.

Thomas started by presenting how JUnit is organised at a high level, supporting both new tests (Jupiter) and old JUnit 4 tests (Vintage).

He went on with the new annotations. Some of them are just a rename of corresponding JUnit 4 annotations. Some others though, are new, for example the @DisplayName annotation that can be used to give a human-readable name to a test method, different than the one infered from the method name. Similarly, JUnit 5 comes with its own list of Assumptions ("lesser" assertions).

An important addition is the Conditional Test Execution. Apart from the baked-in list of conditions (i.e. running only on Linux, or on Java 11, or if environment variable FOO is set to BAR), one can write their own conditions.

Another feature is Tags. By tagging tests, you can run specific subsets of your tests.

Other (seemingly less important) features exist, such as nested tests, test interfaces and default methods. We didn't see much value in them when discussing them, but you may. Let us know if you do.

Finally, JUnit 5 comes with first class support for repeated and parameterized tests, as well as parallel test execution, which promises to make our builds faster.

For additional resources, you can check the sample JUnit 5 projects on [Github](https://github.com/junit-team/junit5-samples), as well as Thomas' [junit repository](https://github.com/pliakas/roukou-junit-features).