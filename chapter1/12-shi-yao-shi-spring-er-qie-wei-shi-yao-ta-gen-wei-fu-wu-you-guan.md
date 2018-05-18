### 1.2 什么是Spring而且为什么它跟微服务有关

Spring has become the de facto development framework for building Java-based applications. At its core, Spring is based on the concept of dependency injection. In a normal Java application, the application is decomposed into classes where each class often has explicit linkages to other classes in the application. The linkages are the invocation of a class constructor directly in the code. Once the code is compiled, these linkage points can’t be changed.

在基于Java的应用的构建当中，Spring已经成为了事实上的开发框架。Spring的核心概念是基于依赖注入。在一个普通的Java应用中，应用被分解成了一个个的类，每个类还与别的类有明显的关联。这些关联是通过在代码中直接调用一个类的构造器而形成的。一旦代码编译好，这些关联点就不能被改变了

This is problematic in a large project because these external linkages are brittle and making a change can result in multiple downstream impacts to other code. A dependency injection framework, such as Spring, allows you to more easily manage large Java projects by externalizing the relationship between objects within your application through convention \(and annotations\) rather than those objects having hard-coded knowledge about each other. Spring sits as an intermediary between the different Java classes of your application and manages their dependencies. Spring essentially lets you assemble your code together like a set of Lego bricks that snap together.

在大型的项目中，这将会产生问题，因为这些外部的关联很脆弱而且做了变动还会对其它代码产生一系列的影响。一个依赖注入框架（如Spring）能让你更容易地去管理大型的Java项目，因为它通过约定好的惯例（还有注解）将你应用内部的对象间的关联在外部就做好了，而不是让这些对象各自将其它对象硬编码在自己的代码里。Spring在应用的不同Java类之间扮演了一个中介的角色，管理这些类之间的依赖。实质上，Spring使得你可以像组装乐高那样将你的代码组装在一起。

> **NOTE** While we cover REST in more detail in chapter 2, the core concept behind REST is that your services should embrace the use of the HTTP verbs \(GET, POST, PUT, and DELETE\) to represent the core actions of the service and use a lightweigh web-oriented data serialization protocol, such as JSON, for requesting and receiving data from the service.
>
> **注意 **我们将在第2章里覆盖更多关于REST的细节，REST的核心概念是你的服务要采用HTTP动词（GET，POST，PUT和DELETE）来表示服务的核心行为，并且使用轻量的面向web的数据序列化协议（如JSON）向服务请求和获取数据。

Because microservices have become one of the more common architectural patterns for building cloud-based applications, the Spring development community has given us Spring Cloud. The Spring Cloud framework makes it simple to operationalize and deploy microservices to a private or public cloud. Spring Cloud wraps several popular cloud-management microservice frameworks under a common framework and makes the use and deployment of these technologies as easy to use as annotating your code. I cover the different components within Spring Cloud later in this chapter.

