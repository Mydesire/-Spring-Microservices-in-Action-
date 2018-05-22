### 1.9.1 核心微服务开发模式

The core development microservice development pattern addresses the basics of building a microservice. Figure 1.8 highlights the topics we’ll cover around basic service design.

![](/assets/figure1.8.png)

**Figure 1.8** When designing your microservice, you have to think about how the service will be consumed and communicated with.

_Service granularity_—How do you approach decomposing a business domain down into microservices so that each microservice has the right level of responsibility? Making a service too coarse-grained with responsibilities that overlap into different business problems domains makes the service difficult to maintain and change over time. Making the service too fine-grained increases the overall complexity of the application and turns the service into a “dumb” data abstraction layer with no logic except for that needed to access the data store. I cover service granularity in chapter 2.

_Communication protocols_—How will developers communicate with your service? Do you use XML \(Extensible Markup Language\), JSON \(JavaScript Object Notation\), or a binary protocol such as Thrift to send data back and forth your microservices? We’ll go into why JSON is the ideal choice for microservices and has become the most common choice for sending and receiving data to microservices. I cover communication protocols in chapter 2.

_Interface design_—What’s the best way to design the actual service interfaces that developers are going to use to call your service? How do you structure your service URLs to communicate service intent? What about versioning your services? A well-design microservice interface makes using your service intuitive. I cover interface design in chapter 2.

_Configuration management of service_—How do you manage the configuration of your microservice so that as it moves between different environments in the cloud you never have to change the core application code or configuration? I cover managing service configuration in chapter 3.

_Event processing between services_—How do you decouple your microservice using events so that you minimize hardcoded dependencies between your services and increase the resiliency of your application? I cover event processing between services in chapter 8.

