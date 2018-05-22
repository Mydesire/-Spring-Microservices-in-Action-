### 1.9.2 微服务路由模式

The microservice routing patterns deal with how a client application that wants to consume a microservice discovers the location of the service and is routed over to it. In a cloud-based application, you might have hundreds of microservice instances running. You’ll need to abstract away the physical IP address of these services and have a single point of entry for service calls so that you can consistently enforce security and content policies for all service calls.

Service discovery and routing answer the question, “How do I get my client’s request for a service to a specific instance of a service?”

* _Service discovery_—How do you make your microservice discoverable so client applications can find them without having the location of the service hardcoded into the application? How do you ensure that misbehaving microservice instances are removed from the pool of available service instances? I cover service discovery in chapter 4.

![](/assets/figure1.9.png)

**Figure 1.9** Service discovery and routing are key parts of any large-scale microservice application.

* _Service routing_—How do you provide a single entry point for all of your services so that security policies and routing rules are applied uniformly to multiple services and service instances in your microservice applications? How do you ensure that each developer in your team doesn’t have to come up with their own solutions for providing routing to their services? I cover service routing in chapter 6.

In figure 1.9, service discovery and service routing appear to have a hard-coded sequence of events between them \(first comes service routing and the service discovery\). However, the two patterns aren’t dependent on one another. For instance, we can implement service discovery without service routing. You can implement service routing without service discovery \(even though its implementation is more difficult\).

