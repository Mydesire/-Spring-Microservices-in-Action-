### 2.6 总结

* To be successful with microservices, you need to integrate in the architect’s, software developer’s, and DevOps’ perspectives.  
  为了成功构建一套微服务，我们需要结合架构师，软件工程师，以及DevOps工程师的观点角度。
* Microservices, while a powerful architectural paradigm, have their benefits and tradeoffs. Not all applications should be microservice applications.  
  微服务虽然是一个强大的架构模式，但它也有它的优点和缺点。并不是所有的应用都可以是微服务应用。
* From an architect’s perspective, microservices are small, self-contained, and distributed. Microservices should have narrow boundaries and manage a small set of data.
  从架构师的角度来看，微服务应该是小的，自包含的，而且是分布式的。微服务应该是窄边界的，管理着少量的数据。
* From a developer’s perspective, microservices are typically built using a RESTstyle of design, with JSON as the payload for sending and receiving data from the service.  
  从开发人员的角度来看，微服务通常采用REST风格的设计来构建，即往服务发送数据或从服务接收数据时用JSON作为负载。
* Spring Boot is the ideal framework for building microservices because it lets you build a REST-based JSON service with a few simple annotations.  
  Spring Boot是构建微服务理想的框架，因为它使得你可以通过几个注解就构建出一个基于REST的JSON服务。
* From a DevOp’s perspective, how a microservice is packaged, deployed, and monitored are of critical importance.  
  从DevOps工程师的角度来看，如何对微服务进行打包，部署，以及监控是非常重要的。
* Out of the box, Spring Boot allows you to deliver a service as a single executable JAR file. An embedded Tomcat server in the producer JAR file hosts the service.  
  Spring Boot开箱即用的特性允许你可以将服务作为单个可执行JAR文件来交付。内嵌在用于生产的JAR文件托管该服务。
* Spring Actuator, which is included with the Spring Boot framework, exposes information about the operational health of the service along with information about the services runtime.  
  包含在Spring Boot框架里的Spring Actuator，可以通过服务运行时的信息来暴露服务的健康状态信息。



