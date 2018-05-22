### 1.9 微服务不仅仅是编写代码

![](/assets/figure1.7.png)**Figure 1.7** Microservices are more than the business logic. You need to think about the environment where the services are going to run and how the services will scale and be resilient.

**图1.7** 微服务不仅仅是业务逻辑。你需要考虑服务将要运行的环境以及服务可以如何扩展和弹性化。

While the concepts around building individual microservices are easy to understand, running and supporting a robust microservice application \(especially when running in the cloud\) involves more than writing the code for the service. Writing a robust service includes considering several topics. Figure 1.7 highlights these topics.

虽然关于构建单独微服务的概念很容易理解，但要运行并支撑一个健壮的微服务应用（尤其是当其运行在云上时）则不仅仅只是编写服务代码了。编写一个健壮的服务包含了好几个需要认真考虑的地方。图1.7展示了这些点。

Let’s walk through the items in figure 1.7 in more detail:

让我们详细看看图1.7里提到的这些条目：

_Right-sized_—How do you ensure that your microservices are properly sized so that you don’t have a microservice take on too much responsibility? Remember, properly sized, a service allows you to quickly make changes to an application and reduces the overall risk of an outage to the entire application.

合适的大小——如何确保微服务的大小是合适的，使得每个微服务的责任都不会太多？记住，大小合适的微服务可以让你对应用做出快速的改变，减少整体应用中断的风险。（译者注：其实就是如何让某个微服务只专注于某个特定责任）

_Location transparent_—How you we manage the physical details of service invocation when in a microservice application, multiple service instances can quickly start and shut down?

位置透明——如何在微服务应用中管理服务调用的物理细节时，多个服务实例可以快速启动和关闭？（译者注：其实就是如何管理微服务的物理位置，使得微服务的增加或移除都不会对服务的客户端造成影响）

_Resilient_—How do you protect your microservice consumers and the overall integrity of your application by routing around failing services and ensuring that you take a “fail-fast” approach?

弹性——如何对失败了的服务进行路由并确保采取“快速失败”的措施，以此保护微服务的消费方以及应用的整体完整性？（译者注：说白了，就是当某个服务出现问题时，如何让它的客户端快速回退）

_Repeatable_—How do you ensure that every new instance of your service brought up is guaranteed to have the same configuration and code base as all the other service instances in production?

可重复性——如何保证每个新添的服务实例的配置及代码与生产上的其它服务实例一致？

_Scalable_—How do you use asynchronous processing and events to minimize the direct dependencies between your services and ensure that you can gracefully scale your microservices?

可扩展性——

This book takes a patterns-based approach as we answer these questions. With a patterns-based approach, we lay out common designs that can be used across different technology implementations. While we’ve chosen to use Spring Boot and Spring Cloud to implement the patterns we’re going to use in this book, nothing will keep you from taking the concepts presented here and using them with other technology platforms. Specifically, we cover the following six categories of microservice patterns:

* Core development patterns

* Routing patterns

* Client resiliency patterns

* Security patterns

* Logging and tracing patterns

* Build and deployment patterns

Let’s walk through these patterns in more detail.

