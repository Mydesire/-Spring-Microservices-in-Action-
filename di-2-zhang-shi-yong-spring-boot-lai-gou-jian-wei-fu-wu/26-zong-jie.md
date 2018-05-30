### 2.6 总结

* To be successful with microservices, you need to integrate in the architect’s, software developer’s, and DevOps’ perspectives.  
  为了成功构建一套微服务，我们需要结合架构师，软件工程师，以及DevOps的观点角度。
* Microservices, while a powerful architectural paradigm, have their benefits and tradeoffs. Not all applications should be microservice applications.  
  微服务虽然是一个强大的架构模式，但它也有它的优点和缺点。并不是所有的应用都可以是微服务应用。
* From an architect’s perspective, microservices are small, self-contained, and distributed. Microservices should have narrow boundaries and manage a small set of data.
  从一个架构师的角度，微服务应该是小的，自包含的，而且是分布式的。
* From a developer’s perspective, microservices are typically built using a RESTstyle of design, with JSON as the payload for sending and receiving data from the service.
* Spring Boot is the ideal framework for building microservices because it lets you build a REST-based JSON service with a few simple annotations.
* From a DevOp’s perspective, how a microservice is packaged, deployed, and monitored are of critical importance.
* Out of the box, Spring Boot allows you to deliver a service as a single executable JAR file. An embedded Tomcat server in the producer JAR file hosts the service.
* Spring Actuator, which is included with the Spring Boot framework, exposes information about the operational health of the service along with information about the services runtime.



