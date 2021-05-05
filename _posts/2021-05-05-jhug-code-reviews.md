---
title: JHUG 22-Apr-2021 discussion on code reviews
date: 2021-05-05T15:00:00+03:00
author: Spiros Anastasopoulos
layout: post
categories:
  - java
tags:
  - community
  - jhug java meetup
---

In our previous [meetup](https://www.jhug.gr/jhug-meetup-april-22th-2021/) we had an open discussion about code reviews. The goal was not to mention patterns, anti-patterns or guidelines but rather to discuss the everyday life of reviewing and how engineers of all levels see the process from both sides, as authors and as reviewers. It was a very interesting session and a lot of opinions were heard. This post is a summary of that discussion.

## Code reviews

You know the drill: An author makes some changes and then submits a PR. One or more reviewers will read it and eventually one or more will give a +1 to the PR and the author will merge it in the main code base. This process can take from a simple [LGTM](https://github.com/songjiayang/review-abbreviation) within an hour, to days arguing around proper grammar rules of comments. Why is there such variance?


It is important to state explicitly what a code review is. Wikipedia defines code review as

> a software quality assurance activity in which one or several people check a program mainly by viewing and reading parts of its source code, and they do so after implementation or as an interruption of implementation.

Let’s explain it starting from the end.

_“After implementation”_ means that the code achieves its purpose, is debugged, the tests pass and the CI/CD bots (linters, formatters etc) are happy. The author should be confident that his work is complete and can be merged without problems. The reviewer should start by assuming that everything is OK. A PR is not the place to discuss design alternatives or debug code or propose UX approaches. All these should be handled in the corresponding parts of the software process. If a bug is found, or if the performance is not acceptable or something like this happens, the reviewer will report it. But if this happens frequently then there is something wrong with the process and must be fixed. Do not ruin the review process by moving other parts of the software process in it.

_“check a program mainly by viewing and reading”_ means exactly this. The reviewer will only read the code and infer an opinion. He is not obliged to debug it, test it, lint it or try it. He must only decide if the code passes the accepted guidelines for code quality and if the assumptions of the code about a business domain are correct.

It is important to note the significance of review guidelines and project documentation. If there are no guidelines then every personal statement and opinion becomes a de facto standard and code quality varies depending on the reviewer. In some organizations, there are no guidelines but the opinions of the first employees are hard wired in the code and are referred as _“this is how we do things here”_. This of course hurts progress since new ideas cannot find their way. It is very important for an organization to have clear, written guidelines for code reviews otherwise the process loses much of its value. The other important note is about documentation. An author new to a code part, does not have documents to read, makes assumptions and these prove wrong when a more experienced coworker makes a code review. If this happens the author returns back to the whiteboard and significant time is lost. Again the code review is not the place for this. Documentation must be updated. It is a mistake to assume that these errors will be caught during PRs. Things change, people come and go and eventually the domain knowledge is lost. 

## Organization culture

Everybody agrees that the reviewing process reflects the culture of an organization. If there are problems here, for sure, they will be reflected in code reviews.

Consider a company with a culture that advocates fast releases of new features and does not promote code quality. In this environment reviews are easy. Everybody gets a +1 just minutes after the submission of the PR and are happy until the day they face the giant technical debt that was accumulated. Now, assume that this company has some engineers that want to do decent code reviews and are not eager to give +1 easily. Because of the culture, the others will avoid them as reviewers and prefer colleagues that give +1 easily. In most cases the culture of the company will prevail and they won’t be able to change something.

Now let’s see a company with another type of toxic culture, this time extreme competition. Everybody wants to prove that he is the best and second to none. Sometimes they even fear for their positions. In this case reviews become hell. Nobody leaves even a single line without a comment and does not approve anything until the author conforms with everything. A PR can have multiple passes and the final approved version is in essence a rewrite according to the reviewer’s opinions. In this case we have also seen notorious comment exchanges between different reviewers until eventually one steps back and let the other dominate the review.

## Organization structure

The structure of an organization also has a direct impact on the review process.

The first example is the almost flat organization. This is the usual case of OSS projects. There is a small team of maintainers that handle all the reviews. Some projects do hard reviews and some others not. In this case the dominating factor is the author type. If he is an occasional committer then an exhaustive review is frustrating for him but necessary on behalf of the project. On the other hand, if the author really wants to engage the project and do open source work, he must do most of the dirty job, learn the guidelines of the community and have patience. After an initial period of _“hard”_ reviews everything becomes easier. Note that in flat organizations everybody can hack any part of the product and thus reviews have variable difficulty degrees. It is not the same to fix typos in the documentation and to fix the performance of an application.

Another example is the usual tree structured organization where everyone has colleagues and supervisors.The personnel is divided into teams and each team has ownership of a part of the product. In this case most PRs are reviewed by the team leader and maybe by another team member. It is the team leader’s duty to guarantee (and/or enforce) code quality and make sure that all team members understand the guidelines of the team. In this case the review process is a one man game and reflects the personality and abilities of the leader. Sometimes he has a lot of work and reviews may be late. Or there are some pending issues that make your review late or not that important. Or he may have some bad days in work (he also has supervisors). Sometimes a TL is new in a team and does not yet have knowledge of the team and the domain. What is important here is that the team is small and works on the same areas. Eventually, and only if the culture of the company is not toxic, they will find a way to cooperate smoothly and efficiently.

## Mentoring

Now, let's discuss another important aspect of code reviews, the skills gap between an author and a reviewer. There are two cases.

The first and most common, is when the reviewer is more skilled than the author either because in general he is a better engineer or he is more experienced with the code base. The worst thing a reviewer can do is to emphasize his authority and intimidate the author. The keyword is mentoring. The reviewer must be willing to help the author narrow the skills gap by providing valuable help. An organization should hire persons with such mentality, this qualification is a matter of character and cannot be learned. Of course you cannot expect everyone to have it. There are some great engineers that lack this soft skill but this must be the exception and not the norm.

The second case of the gap is when the author is more skilled. This is done to give the reviewer a chance to see some expert code in an area he is not well acquainted with. This gives him the opportunity to study the area, the code, the techniques and learn. Moreover he learns a lot about the review process and the internal guidelines since he addresses a more skilled individual and thus he must behave accordingly. The keyword is again mentoring, this time on behalf of the author. This second case has an interesting variation. Senior engineers have a tendency to dive in complexity, many times unnecessarily. The best way to address this is to have their work reviewed by a lesser expert. A single comment like _“I cannot understand this, too complex”_ or _“why not simplify like this”_ is very valuable as it acts as an alarm to them that they have gone too far.

## Mentality

We discuss last but not least the mentality that should govern authors and reviewers.

The code review is a software quality assurance tool. It is a highly subjective procedure that involves people exchanging opinions on a topic. As such it can go astray easily.

First of all it needs respect for the work under review. The author worked many hours on it, is pleased with the result and looks forward to merge it in the code base. As a reviewer you don’t have the right to underestimate this effort and as an author you should not present to the reviewer duct tape patches or work in progress. And remember that giving praise to good work has great value for all.

Then comes willingness to learn and willingness to teach. During a good review you learn a lot about API and data design, good coding practices and the domain. There will be always both better and worse engineers than you. If this does not happen then you are not evolving. You must be eager to learn from good advice and you must be ready to consult anybody who asks.

Finally there is the improvement culture. We do reviews to improve both as individuals and as organizations. It is of no value to exchange compliments and bypass code sins. If we are not improving then we are doing something wrong. Sometimes we must _“break some eggs”_ and do some hard code reviews, by pointing bad points with a vigor and by accepting well behaved critique.

## Practical considerations

In the discussion we also identified some practical issues that occur frequently in the PRs. We mention them in bullets because most of them are discussed in depth in many good books and posts about code reviews.
* PRs must be fast. Having a PR open for many days and moving back and forth between the PR and other tasks means a lot of daily context switches and practical problems during the final merge as the fork may have been outdated.
* Reviewers should review tests with the same care as the code. Many times a PR focuses on the code while the tests are inadequate and this stays unnoticed.
* Focus on the essence of the PR. It is very easy to get distracted on low hanging fruits like style, comments, certain patterns etc
* Personal opinions are not guidelines for all and an author can ignore them.
* Multi pass PRs are very annoying. Try to make all your comments in one pass and accept when the author makes the fixes.
* Reviews and tests go hand to hand. You should not exaggerate on reviews to hide the lack of tests and vice versa.
* People who cause problems during reviews for sure will cause problems and in other areas. The inverse also holds. Problematic characters won’t wait for reviews to show up.

## Conclusions

We can say that reviews are not perfect but currently it is one of the best tools in our disposal to guarantee software quality. It requires a proper mentality from all to get the best results. Remember that it involves people discussing opinions and in modern civilization there is no single domain in which people discuss and the process is useful, straightforward and smooth. Just look at forums, social media, not to mention TV panels or even the parliaments of the countries. So until AI evolves to the point where we can assign a code review to `codeJudge 42` all we should do is read each other’s code with respect and empathy.
