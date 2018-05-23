### 1.13 总结

* Microservices are extremely small pieces of functionality that are responsible for one specific area of scope.

* 微服务都是很小的功能模块，每个微服务只负责小范围的责任。

* No industry standards exist for microservices. Unlike other early web service protocols, microservices take a principle-based approach and align with the concepts of REST and JSON.

* 目前微服务并没有现成的工业标准。与其它早期的web服务协议不同，微服务采取了基于原则的方式，并与REST和JSON进行结合。

* Writing microservices is easy, but fully operationalizing them for production requires additional forethought. We introduced several categories of microservice development patterns, including core development, routing patterns, client resiliency, security, logging, and build/deployment patterns.

* 编写微服务不难，但若要使这些微服务充分运作，则需要额外的前瞻性。在前面我们介绍了几个微服务开发模式，包括核心开发，路由模式，客户端弹性，安全，日志，以及构建/部署模式。

* While microservices are language-agnostic, we introduced two Spring frameworks that significantly help in building microservices: Spring Boot and Spring Cloud.

* Spring Boot is used to simplify the building of REST-based/JSON microservices. Its goal is to make it possible for you to build microservices quickly with nothing more than a few annotations.

* Spring Cloud is a collection of open source technologies from companies such as Netflix and HashiCorp that have been “wrapped” with Spring annotations to significantly simplify the setup and configuration of these services.



