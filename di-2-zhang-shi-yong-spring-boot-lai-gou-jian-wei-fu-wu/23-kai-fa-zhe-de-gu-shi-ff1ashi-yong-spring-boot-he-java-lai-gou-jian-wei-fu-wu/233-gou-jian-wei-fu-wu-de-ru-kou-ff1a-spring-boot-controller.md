### 2.3.3 构建微服务的入口：Spring Boot controller

Now that you’ve gotten the build script out of the way and implemented a simple Spring Boot Bootstrap class, you can begin writing your first code that will do something. This code will be your Controller class. In a Spring boot application, a Controller class exposes the services endpoints and maps the data from an incoming HTTP request to a Java method that will process the request.

> **Give it a REST  
> **
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

> **Why JSON for microservices?**
>
> Multiple protocols can be used to send data back and forth between HTTP-based microservices. JSON has emerged as the de facto standard for several reasons.
>
> First, compared to other protocols such as the XML-based SOAP \(Simple Object Access Protocol\), it’s extremely lightweight in that you can express your data without having much textual overhead.
>
> Second, it’s easily read and consumed by a human being. This is an underrated quality for choosing a serialization protocol. When a problem arises, it’s critical for developers to look at a chunk of JSON and quickly, visually process what’s in it. The simplicity of the protocol makes this incredibly easy to do.
>
> Third, JSON is the default serialization protocol used in JavaScript. Since the dramatic rise of JavaScript as a programming language and the equally dramatic rise of Single Page Internet Applications \(SPIA\) that rely heavily on JavaScript, JSON has become a natural fit for building REST-based applications because it’s what the frontend web clients use to call services.
>
> Other mechanisms and protocols are more efficient than JSON for communicating between services. The Apache Thrift \(http://thrift.apache.org\) framework allows you to build multi-language services that can communicate with one another using a binary protocol. The Apache Avro protocol \(http://avro.apache.org\) is a data serialization protocol that converts data back and forth to a binary format between client and server calls.
>
> If you need to minimize the size of the data you’re sending across the wire, I recommend you look at these protocols. But it has been my experience that using straightup JSON in your microservices works effectively and doesn’t interpose another layer of communication to debug between your service consumers and service clients.

The second annotation shown in listing 2.3 is the @RequestMapping annotation. You can use the @RequestMapping annotation as a class-level and method-level annotation. The @RequestMapping annotation is used to tell the Spring container the HTTP endpoint that the service is going to expose to the world. When you use the class-level @RequestMapping annotation, you’re establishing the root of the URL for all the other endpoints exposed by the controller.

In listing 2.3, the @RequestMapping\(value="/v1/organizations/{organizationId}/licenses"\) uses the value attribute to establish the root of the URL for all endpoints exposed in the controller class. All service endpoints exposed in this controller will start with /v1/organizations/{organizationId}/licenses as the root of their endpoint. The {organizationId} is a placeholder that indicates how you expect the URL to be parameterized with an organizationId passed in every call. The use of organizationId in the URL allows you to differentiate between the different customers who might use your service.

Now you’ll add the first method to your controller. This method will implement the GET verb used in a REST call and return a single License class instance, as shown in the following listing. \(For purposes of this discussion you’ll instantiate a Java class called License.\)

