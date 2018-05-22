### 1.9.3 微服务客户端弹性模式

Because microservice architectures are highly distributed, you have to be extremely sensitive in how you prevent a problem in a single service \(or service instance\) from cascading up and out to the consumers of the service. To this end, we’ll cover four client resiliency patterns:

* _Client-side load balancing_—How do you cache the location of your service instances on the service client so that calls to multiple instances of a microservice are load balanced to all the health instances of that microservice?

* _Circuit breakers pattern_—How do you prevent a client from continuing to call a service that’s failing or suffering performance problems? When a service is running slowly, it consumes resources on the client calling it. You want failing microservice calls to fail fast so that the calling client can quickly respond and take an appropriate action.

* _Fallback pattern_—When a service call fails, how do you provide a “plug-in” mechanism that will allow the service client to try to carry out its work through alter- native means other than the microservice being called?

* _Bulkhead pattern_—Microservice applications use multiple distributed resources to carry out their work. How do you compartmentalize these calls so that the mis- behavior of one service call doesn’t negatively impact the rest of the application?

由于微服务架构是高度分散的，你必须对这个问题保持高度的敏感性，那就是如何防止某个服务（或者服务实例）里出现的问题逐层呈现给该服务的消费方。为此，我们将介绍四种客户端弹性模式：

* 客户端负载均衡——如何将服务实例的位置在服务客户端上缓存起来，以使多个微服务实例的调用可以被负载均衡到该服务的健康实例上？
* 断路器模式——当某个服务发生故障或者遇到性能问题时，如何防止客户端继续调用它？当一个服务运行很慢时，它将消耗正在消费它的客户端上的资源。此时，你应该让发生了故障的微服务调用

**Figure 1.10** With microservices, you must protect the service caller from a poorly behaving service. Remember, a slow or down service can cause disruptions beyond the immediate service.

Figure 1.10 shows how these patterns protect the consumer of service from being impacted when a service is misbehaving. I cover these four topics in chapter 5.

