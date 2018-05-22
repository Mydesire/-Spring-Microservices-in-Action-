### 1.9.2 微服务路由模式

The microservice routing patterns deal with how a client application that wants to consume a microservice discovers the location of the service and is routed over to it. In a cloud-based application, you might have hundreds of microservice instances running. You’ll need to abstract away the physical IP address of these services and have a single point of entry for service calls so that you can consistently enforce security and content policies for all service calls.

微服务路由模式处理的是消费微服务的客户端应用如何发现服务位置以及如何路由过去的问题。在基于云的应用里，你可能会有几百个微服务实例在运行。你需要对这些服务的物理IP地址进行抽象，并且为服务调用提供单一的入口，这样，就可以为所有的服务调用持续实施安全保证以及内容策略。

Service discovery and routing answer the question, “How do I get my client’s request for a service to a specific instance of a service?”

服务发现和路由回答了这么一个问题，“我要如何获得客户端发起的对某个特定服务实例的请求？”

* _Service discovery_—How do you make your microservice discoverable so client applications can find them without having the location of the service hardcoded into the application? How do you ensure that misbehaving microservice instances are removed from the pool of available service instances? I cover service discovery in chapter 4.
* 服务发现——要如何才能让你的微服务可被发现，从而让客户端应用可以不用将服务的位置硬编码进应用里就可以发现这些微服务？如何保证出错的微服务实例从可用服务实例池里移除了？我将在第4章讨论服务发现。

![](/assets/figure1.9.png)

**Figure 1.9** Service discovery and routing are key parts of any large-scale microservice application.

**图1.9 **服务发现和路由是任何大规模微服务应用的关键部分。

* _Service routing_—How do you provide a single entry point for all of your services so that security policies and routing rules are applied uniformly to multiple services and service instances in your microservice applications? How do you ensure that each developer in your team doesn’t have to come up with their own solutions for providing routing to their services? I cover service routing in chapter 6.
* 服务路由——如何为所有的服务提供单一的入口，使得安全策略和路由规则可以用于你的微服务应用的多个服务和服务实例？如何确保小组里的每个开发人员不必提供自己的路由到他们服务的方案？我将在第6章讨论服务路由。

In figure 1.9, service discovery and service routing appear to have a hard-coded sequence of events between them \(first comes service routing and the service discovery\). However, the two patterns aren’t dependent on one another. For instance, we can implement service discovery without service routing. You can implement service routing without service discovery \(even though its implementation is more difficult\).

在图1.9里，服务发现和服务路由。但是，这两种模式是互相独立的。例如，我们可以只实现服务发现，而不用实现服务路由。你可以实现服务路由，但不实现服务发现（虽然服务路由的实现跟难一些）。

