---
title: JHUG 11-Mar-2021 virtual meetup
date: 2021-03-12T19:00:00+02:00
author: Spiros Anastasopoulos
layout: post
categories:
  - java
tags:
  - community
  - jhug java meetup
---
This Thursday 31/03 we had the first virtual meetup of 2021. We were happy to meet once again, although virtually from our homes, and discuss interesting topics about java. The covid-19 lockdown has been going on for almost a year and it will continue for some more months for sure. However JHUG is active and we keep having meetups and we would like to thank our members for their patience and eagerness to participate in the events.

Now, lets go to the talks. The latest meetup had 3.

## Let’s talk about Bean Mapping

The first talk was by [Periklis Ntanasis](https://www.linkedin.com/in/pntanasis/) on java bean mapping. This is a frequent issue on data design. We have objects of different clases but with some common properties, and we want to map one object to the other. There are many uses cases. The most common are when we want to create DTOs for performance reasons or _map_ an object to another class to take advantage of the annotations of the later. Periklis presented the problem and discussed the pros and cons of each approach: manual, reflection, code generation, byte code instrumentation. He also made a survey of almost all(!) available libraries, commented on each one and presented performance benchmarks. That was a very interesting talk not only because it was concise and up to the point but because it reminded to us that exploring a solution space even after a good solution is already presented can be fun and joyful.

You can find the slides [here](https://github.com/JHUG/JHUG-General-Resources/blob/master/presentations/2021/03-March/JavaBeanMapping.pdf). Moreover Periklis has written a blog post about the topic which you can read [here](https://masterex.github.io/archive/2021/02/08/java-bean-mapping-in-depth.html).

## Test && commit || revert

The second talk was by [Nikos Voulgaris](https://www.linkedin.com/in/nikos-voulgaris-44455546/) on a new programming workflow called `test && commit || revert`. That workflow was introduced by Kent Beck in this [post](https://medium.com/@kentbeck_7670/test-commit-revert-870bbd756864) and is new and relatively untried. We can describe it as an extension of TDD to include git: If the tests pass then commit else revert. This is however a simplification that does injustice to the flow. Nikos fully explained the flow, how it relates to TDD and most importantly the state of mind that enforces to the programmer. This is in essence its value. It is not a technical pattern but a discipline that the programmer must obey to make sure he makes small, sure, steady steps while coding. The talk was very vivid and caused an interesting Q&A session. That was expected because each programmer has its own _accepted_ workflow and is always at least _suspicious_ when presented with something outside the _one-true-way_.

You can find the slides [here](https://github.com/JHUG/JHUG-General-Resources/blob/master/presentations/2021/03-March/TestCommitRevert.pdf). Nikos also published a blog post about the flow which you can read [here](https://nvoulgaris.com/test--commit--revert/).

## Developing native CLI applications with Quarkus and PicoCLI

The third talk by [Georgios Andrianakis](https://www.linkedin.com/in/georgios-andrianakis/) was about [picocli](https://picocli.info/) a library for building rich command line applications in java. When we say rich apps we mean something like `git` which has subcommands like `git add`, `git commit` etc and not something like `gcc` which is a single command but with a lot, really a lot, of flags. Picocli, is a declarative library, that is you write properly annotated classes and the entry points for the commands and then the framework generates the app sceleton for you. This sceleton app of course should be augmented with the business logic. There are many ways to do it: plain java, spring, micronaut or any other framework. Georgios chose to present the integration with [quarkus](https://www.redhat.com/en/topics/cloud-native-apps/what-is-quarkus) which has 2 strong points: The first is that is supports CDI (Contexts and Dependency Injection) out of the box and the second is that it can generate a GraalVM native image which offers very small startup time and fast execution times for the app. All these are provided by quarkus with minimal configuration.

The talk was mostly live coding but you can find a guide for setting up quarkus with picocli [here](https://quarkus.io/guides/picocli).

## That's all folks

We had a great time with the talks and the vivid Q&A sessions. You are now planning the next meetup which will be virtual again. The details will be published in our [slack](https://jhug.slack.com) channel. You should consider joining our slack because this is our home during the lockdown and we have very interesting discussions and sometimes great flame wars. So, until our next meetup, stay well, take care of yourselves and keep coding.
