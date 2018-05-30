### 2.6 总结

* To be successful with microservices, you need to integrate in the architect’s, software developer’s, and DevOps’ perspectives.
* Microservices, while a powerful architectural paradigm, have their benefits and tradeoffs. Not all applications should be microservice applications.
* From an architect’s perspective, microservices are small, self-contained, and distributed. Microservices should have narrow boundaries and manage a small set of data.
* From a developer’s perspective, microservices are typically built using a RESTstyle of design, with JSON as the payload for sending and receiving data from the service.
* Spring Boot is the ideal framework for building microservices because it lets you build a REST-based JSON service with a few simple annotations.
* From a DevOp’s perspective, how a microservice is packaged, deployed, and monitored are of critical importance.
* Out of the box, Spring Boot allows you to deliver a service as a single executable JAR file. An embedded Tomcat server in the producer JAR file hosts the service.
* Spring Actuator, which is included with the Spring Boot framework, exposes information about the operational health of the service along with information about the services runtime.



