### 2.3.3 构建微服务的入口：Spring Boot controller

Now that you’ve gotten the build script out of the way and implemented a simple Spring Boot Bootstrap class, you can begin writing your first code that will do something. This code will be your Controller class. In a Spring boot application, a Controller class exposes the services endpoints and maps the data from an incoming HTTP request to a Java method that will process the request.

> **Give it a REST**
>
> All the microservices in this book follow the REST approach to building your services. An in-depth discussion of REST is outside of the scope this book,a but for your purposes, all the services you build will have the following characteristics:
>
> Use HTTP as the invocation protocol for the service—The service will be exposed via HTTP endpoint and will use the HTTP protocol to carry data to and from the services.
>
> Map the behavior of the service to standard HTTP verbs—REST emphasizes having services map their behavior to the HTTP verbs of POST, GET, PUT, and DELETE verbs. These verbs map to the CRUD functions found in most services.
>
> Use JSON as the serialization format for all data going to and from the service—This isn’t a hard-and-fast principle for REST-based microservices, but JSON has become lingua franca for serializing data that’s going to be submitted and returned by a microservice. XML can be used, but many REST-based applications make heavy use of JavaScript and JSON \(JavaScript Object Notation\). JSON is the native format for serializing and deserializing data being consumed by JavaScript-based web front-ends and services.
>
> Use HTTP status codes to communicate the status of a service call—The HTTP protocol has developed a rich set of status codes to indicate the success or failure of a service. REST-based services take advantage of these HTTP status codes and other webbased infrastructure, such as reverse proxies and caches, which can be integrated with your microservices with relative ease.
>
> HTTP is the language of the web and using HTTP as the philosophical framework for building your service is a key to building services in the cloud.

Your first controller class is located in src/main/java/com/thoughtmechanix/licenses/controllers/LicenseServiceController.java. This class will expose four HTTP endpoints that will map to the POST, GET, PUT, and DELETE verbs.

Let’s walk through the controller class and look at how Spring Boot provides a set of annotations that keeps the effort needed to expose your service endpoints to a minimum and allows you to focus on building the business logic for the service. We’ll start by looking at the basic controller class definition without any class methods in it yet. The following listing shows the controller class that you built for your licensing service.

Listing 2.3 Marking the LicenseServiceController as a Spring RestController

```java
package com.thoughtmechanix.licenses.controllers;
import … // Removed for conciseness

@RestController
@RequestMapping(value="/v1/organizations/{organizationId}/licenses")
public class LicenseServiceController {
//Body of the class removed for conciseness
}
```

We’ll begin our exploration by looking at the @RestController annotation. The @RestController is a class-level Java annotation and tells the Spring Container that this Java class is going to be used for a REST-based service. This annotation automatically handles the serialization of data passed into the services as JSON or XML \(by default the @RestController class will serialize returned data into JSON\). Unlike the traditional Spring @Controller annotation, the @RestController annotation doesn’t require you as the developer to return a ResponseBody class from your controller class. This is all handled by the presence of the @RestController annotation, which includes the @ResponseBody annotation.

