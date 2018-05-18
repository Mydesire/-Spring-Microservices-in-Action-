### 1.5 用Spring Boot构建一个微服务

I’ve always had the opinion that a software development framework is well thoughtout and easy to use if it passes what I affectionately call the “Carnell Monkey Test.” If a monkey like me \(the author\) can figure out a framework in 10 minutes or less, it has promise. That’s how I felt the first time I wrote a sample Spring Boot service. I want you to have to the same experience and joy, so let’s take a minute to see how to write a simple “Hello World” REST-service using Spring Boot.

我总是持着这么一个观点：一个软件开发框架是经过仔细考虑的，而且如果它经过了卡内尔猴子测试（译者注：Carnell Monkey Test，作者对它的昵称）的话，那么它应该是易用的。如果一个首次接触的人可以在十分钟之内弄明白一个框架，那么它就保证了易用性这一点。我第一次写Spring Boot服务示例时就感受到了这点。我希望你也有相同感受和乐趣，所以我们花一分钟来看看如何用Spring Boot写一个简单的”Hello World”REST服务。

In this section, we’re not going to do a detailed walkthrough of much of the code presented. Our goal is to give you a taste of writing a Spring Boot service. We’ll go into much more detail in chapter 2.

在本节里，我们不会过多深入研究展示出来的代码。我们的目的是让你体验一下编写一个Spring Boot服务。我们将在第2章进行更细致的讨论。

Figure 1.3 shows what your service is going to do and the general flow of how Spring Boot microservice will process a user’s request.

图1.3展示了你的服务将要做什么，以及一般情况下Spring Boot微服务是如何处理用户的请求的。

This example is by no means exhaustive or even illustrative of how you should build a production-level microservice, but it should cause you to take a pause because of how little code it took to write it. We’re not going to go through how to set up the project build files or the details of the code until chapter 2. If you’d like to see the Maven pom.xml file and the actual code, you can find it in the chapter 1 section of the downloadable code. All the source code for chapter 1 can be retrieved from the GitHub repository for the book at [https://github.com/carnellj/spmia-chapter1](https://github.com/carnellj/spmia-chapter1).

