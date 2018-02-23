---
id: 131
title: 'Book review &#8211; Hadoop real world solutions  (Packt)'
date: 2013-06-01T12:56:38+02:00
author: papo
layout: post
guid: http://www.jhug.gr/?p=131
permalink: /archives/131
categories:
  - book
---
<p dir="ltr" id="docs-internal-guid-4998a435-ff5f-fe29-e354-05521da44936">
  Nowadays, many developers are starting discussing and using Hadoop framework to solve different problems in big data and Hadoop space. Many tools and practices, are existing and is very difficult for a developer to choose the appropriate tool/approach for his project. This book provides important information not only to non-experience developers but also to experienced ones, since it covers a wide variety of Hadoop-related tools, software frameworks and best practices, like Apache Hive, Pig, MapReduce, HDFS, Giraph and others.
</p>

<p dir="ltr">
  Τhe choice of examples is done very carefully and I think that is quite successful and accurate, because they provide to the reader, including experience and non-experience developers, all the needed information to understand the tools and its usage. The structure of each chapter with the topics of “Getting Ready”, “How to do it” and “How it works” is  very efficient, since it breaks the deal problem into discrete steps and helps also the reader to understand the provided information.  As a suggestion, it would very helpful to add a topic “How to test it” in each chapter.
</p>

<p dir="ltr">
  The organization of the chapters is very good, since it has been separated in logic areas, like importing/export data, make operations and analysis and finally administration and persistence. Personally, I would prefer the chapters of  the administration and persistence (Chapters 9 & 10)  to be in the beginning instead of the end, since the operations that are described can be needed at any time in the book.
</p>

<p dir="ltr">
  <strong>Let’s go to chapters:</strong>
</p>

<p dir="ltr">
  <strong>Chapters 1 &#8211; 3</strong>, are covering topics regarding Importing, Exporting, Extracting and Transforming  data to/from HDFS, by providing several approaches including importing data from MySQL, MS SQL Server and MongoDB. Interesting also is the Chapter 3 which show the how to use tools, like Hive and Pig, MapReduce Java API in order to perform batch-process in data samples and produce transformed data outputs.  Personally I found very interesting, the provided information regarding the extension of Pig to support and use Hadoop Streaming API for time series analytics. Another interesting topic is the usage of Protocol Buffers, which actually helps you to generate binding in different languages (something that you will  needed a lot, dealing with big data systems).
</p>

<p dir="ltr">
  <strong>Chapters 4 &#8211; 5,</strong> are focused to provide information how to perform operations that are needed when you have to deal with bg data and you will always meet these tasks. The chapters are covering a wide range of operations,  from string concatenation and external table mapping to advanced joins. The chapter 5 is very useful, since the these joins are not so trivial (based on my previous experience) , and the reader will find important information regarding this topic and the provided “recipes” from more than one tool (Apache Pig and Hive).
</p>

**Chapter 6-7**, present a few big data problems and provide solutions how to cope  these problems, using Apache Hive and Pig, and Apache Mahout and Girard for applying  and running machine-learning algorithms in large-scale systems. In general this topic is very difficult, and requires a strong theoretical and technical background. The understanding of the code examples, which actually help the reader to understand the concept, and can easily be extended to larger and more complicated problems. These chapters can be used also as the entry point, for more detailed study of big data analytics.

<p dir="ltr">
  <strong>Chapter 8,</strong> my favourite one, is presenting how to troubleshoot and test MapReduce jobs. Since testing and troubleshooting is very important, and sometimes can be very painful, this chapter provides all the needed information regarding tools and techniques, how to debug MapReduce jobs, but also how to write your own tests. This chapter is very rare in most of the books, and is very important to all developers. For
</p>

**Chapter 9** &#8211; 10, are discussing topics regarding maintenance, configuration and administration of Hadoop clusters, including also some fine/job tuning hints. It is also presented technologies regarding the storage of big-data, having in mind also scalability and distributions.  
Overall this is a great book, or better a cookbook, that provides real solutions to the reader. The code examples are very carefully selected to address the presented topic. It covers a wide range of tools and best practices, and can help developers to understand and use these tools.  I think authors managed to understand the need of the developers and provide the appropriate information.

Thomas Pliakas

[Book link](http://www.packtpub.com/hadoop-real-world-solutions-cookbook/book)