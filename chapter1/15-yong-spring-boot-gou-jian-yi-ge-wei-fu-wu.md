### 1.5 用Spring Boot构建一个微服务

I’ve always had the opinion that a software development framework is well thoughtout and easy to use if it passes what I affectionately call the “Carnell Monkey Test.” If a monkey like me \(the author\) can figure out a framework in 10 minutes or less, it has promise. That’s how I felt the first time I wrote a sample Spring Boot service. I want you to have to the same experience and joy, so let’s take a minute to see how to write a simple “Hello World” REST-service using Spring Boot.

我总是持着这么一个观点：一个软件开发框架是经过仔细考虑的，而且如果它经过了卡内尔猴子测试（译者注：Carnell Monkey Test，作者对它的昵称）的话，那么它应该是易用的。如果一个首次接触的人可以在十分钟之内弄明白一个框架，那么它就保证了易用性这一点。我第一次写Spring Boot服务示例时就感受到了这点。我希望你也有相同感受和乐趣，所以我们花一分钟来看看如何用Spring Boot写一个简单的”Hello World”REST服务。

In this section, we’re not going to do a detailed walkthrough of much of the code presented. Our goal is to give you a taste of writing a Spring Boot service. We’ll go into much more detail in chapter 2.

在本节里，我们不会过多深入研究展示出来的代码。我们的目的是让你体验一下编写一个Spring Boot服务。我们将在第2章进行更细致的讨论。

Figure 1.3 shows what your service is going to do and the general flow of how Spring Boot microservice will process a user’s request.

图1.3展示了你的服务将要做什么，以及一般情况下Spring Boot微服务是如何处理用户的请求的。

This example is by no means exhaustive or even illustrative of how you should build a production-level microservice, but it should cause you to take a pause because of how little code it took to write it. We’re not going to go through how to set up the project build files or the details of the code until chapter 2. If you’d like to see the Maven pom.xml file and the actual code, you can find it in the chapter 1 section of the downloadable code. All the source code for chapter 1 can be retrieved from the GitHub repository for the book at [https://github.com/carnellj/spmia-chapter1](https://github.com/carnellj/spmia-chapter1).

这个例子并不是完整详尽的，它甚至无法说明你应该如何构建一个生产级别的微服务，但它应该能让你愣住一会，因为它需要写的代码是如此之少。在进入到第2章之前，我们将不进行关于如何建立项目构建文件或者代码细节的讨论。如果你想看Maven的pom.xml文件以及完整的代码，你可以在第1章节的代码里找到。第1章的所有源代码都可以从本书的Github仓库里获取，地址是[https://github.com/carnellj/spmia-chapter1](https://github.com/carnellj/spmia-chapter1)。

> **NOTE** Please make sure you read appendix A before you try to run the code  
>  examples for the chapters in this book. Appendix A covers the general project layout of all the projects in the book, how to run the build scripts, and  
>  how to fire up the Docker environment. The code examples in this chapter  
>  are simple and designed to be run natively right from your desktop without  
>  the information in additional chapters. However, in later chapters you’ll  
>  quickly begin using Docker to run all the services and infrastructure used in  
>  this book. Don’t go too far into the book without reading appendix A on setting up your desktop environment.
>
> **注意** 在运行本书的代码前请先确保阅读了附录A。附录A涵盖的内容有，本书所有项目的通用项目结构，如何运行构建脚本以及如何启动Docker环境。本章的样例代码很简单，而且它就是被设计成可以直接在你的本机桌面上运行，用不到其它章节的知识。但是，后面的章节你将通过Docker快速启动所有的服务以及书中用到的基础组件。在继续往下读之前，请先阅读附录A，学习如何设置桌面环境。

![](/assets/figure1.3.png)**Figure 1.3** Spring Boot abstracts away the common REST microservice task \(routing to business logic, parsing HTTP parameters from the URL, mapping JSON to/from Java Objects\), and lets the developer focus on the business logic for the service.

**图1.3 **Spring Boot将通用的REST微服务任务进行了抽象（包括路由到业务逻辑，从URL里解析HTTP参数，将JSON和Java对象进行相互映射），从而让开发者专注于服务的业务逻辑。

For this example, you’re going to have a single Java class called simpleservice/src/com/thoughtmechanix/application/simpleservice/Application.java that will be used to expose a REST endpoint called /hello.

在这个例子中，你将看到一个Java类，其类名路径为simpleservice/src/com/thoughtmechanix/application/simpleservice/Application.java，它将被用来暴露一个叫/hello的REST端点。

The following listing shows the code for Application.java.

下面是Application.java的代码。

```java
// Listing 1.1 Hello World with Spring Boot: a simple Spring microservice
package com.thoughtmechanix.simpleservice;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;
import org.springframework.web.bind.annotation.PathVariable;

@SpringBootApplication // 告诉Spring Boot框架这个类是Spring Boot服务的入口
@RestController        // 告诉Spring Boot你将把这个类的代码暴露为一个Spring RestController类
@RequestMapping(value="hello")    // 所有暴露给这个应用的URL将以/hello开头
public class Application {
    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
    // Spring Boot将把这个端口暴露为一个基于GET方法的REST端口，这个端口
    // 接收两个参数：firstName和lastName
    @RequestMapping(value="/{firstName}/{lastName}", method = RequestMethod.GET)
    // 将传入URL的参数firstName和lastName映射为传给hello函数的两个变量
    public String hello( @PathVariable("firstName") String firstName,
                         @PathVariable("lastName") String lastName) {
        // 返回一个手工构建的JSON字符串。在第2章里你将不用创建任何JSON                 
        return String.format("{\"message\":\"Hello %s %s\"}", firstName, lastName);
    }

}
```



