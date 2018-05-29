### 

### 2.3 开发者的故事：使用Spring Boot和Java来构建微服务

When building a microservice, moving from the conceptual space to the implementation space requires a shift in perspective. Specifically, as a developer, you need to establish a basic pattern of how each of the microservices in your application is going to be implemented. While each service is going to be unique, you want to make sure that you’re using a framework that removes boilerplate code and that each piece of your microservice is laid out in the same consistent fashion.

在构建微服务时，从概念到实现的需要观点上的转变。特别地，作为一个开发人员，你需要建立一个关于应用的每个微服务如何实现的基本模式。虽然每个服务都是不同的，但你需要确保你正在使用的框架帮你移除了模板代码，而且每个微服务的形式是一样的。

In this section, we’ll explore the developer’s priorities in building the licensing microservice from your EagleEye domain model. Your licensing service is going to be written using Spring Boot. Spring Boot is an abstraction layer over the standard Spring libraries that allows developers to quickly build Groovy- and Java-based web applications and microservices with significantly less ceremony and configuration than a full-blown Spring application.

在这一节里，我们将探索，依据鹰眼域模型（Eagle domain model）来构建授权微服务（licensing microservice）时，开发人员的优先级顺序。授权微服务将采用Spring Boot来编写。Spring Boot是位于标准Spring库之上的抽象层，它使得开发人员可以快速构建出基于Groovy和Java的web应用以及微服务，而且，比起传统的Spring应用，Spring Boot所需的仪式和配置少很多。

For your licensing service example, you’ll use Java as your core programming language and Apache Maven as your build tool.

对于授权服务这个例子，我们将采用Java作为核心编程语言，Apache Maven作为构建工具。

Over the next several sections you’re going to

1. Build the basic skeleton of the microservice and a Maven script to build the application
2. Implement a Spring bootstrap class that will start the Spring container for the microservice and initiate the kick-off of any initialization work for the class
3. Implement a Spring Boot controller class for mapping an endpoint to expose the endpoints of the service



