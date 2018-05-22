### 1.9 微服务不仅仅是编写代码

![](/assets/figure1.7.png)**Figure 1.7** Microservices are more than the business logic. You need to think about the environment where the services are going to run and how the services will scale and be resilient.

**图1.7** 微服务不仅仅是业务逻辑。你需要考虑服务将要运行的环境以及服务可以如何扩展和弹性化。

While the concepts around building individual microservices are easy to understand, running and supporting a robust microservice application \(especially when running in the cloud\) involves more than writing the code for the service. Writing a robust service includes considering several topics. Figure 1.7 highlights these topics.

Let’s walk through the items in figure 1.7 in more detail:

_Right-sized_—How do you ensure that your microservices are properly sized so that you don’t have a microservice take on too much responsibility? Remember, properly sized, a service allows you to quickly make changes to an application and reduces the overall risk of an outage to the entire application.

_Location transparent_—How you we manage the physical details of service invocation when in a microservice application, multiple service instances can quickly start and shut down?

_Resilient_—How do you protect your microservice consumers and the overall integrity of your application by routing around failing services and ensuring that you take a “fail-fast” approach?

_Repeatable_—How do you ensure that every new instance of your service brought up is guaranteed to have the same configuration and code base as all the other service instances in production?

_Scalable_—How do you use asynchronous processing and events to minimize the direct dependencies between your services and ensure that you can gracefully scale your microservices?

This book takes a patterns-based approach as we answer these questions. With a patterns-based approach, we lay out common designs that can be used across different technology implementations. While we’ve chosen to use Spring Boot and Spring Cloud to implement the patterns we’re going to use in this book, nothing will keep you from taking the concepts presented here and using them with other technology platforms. Specifically, we cover the following six categories of microservice patterns:

* Core development patterns

* Routing patterns

* Client resiliency patterns

* Security patterns

* Logging and tracing patterns

* Build and deployment patterns

Let’s walk through these patterns in more detail.

