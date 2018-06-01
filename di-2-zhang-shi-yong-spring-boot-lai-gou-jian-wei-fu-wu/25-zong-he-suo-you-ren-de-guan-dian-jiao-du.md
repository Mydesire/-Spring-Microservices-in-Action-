### 2.5 综合所有人的观点角度

Microservices in the cloud seem deceptively simple. But to be successful with them, you need to have an integrated view that pulls the perspective of the architect, the developer, and DevOps engineer together into a cohesive vision. The key takeaways for each of these perspectives are

1. _Architect_—Focus on the natural contours of your business problem. Describe your business problem domain and listen to the story you’re telling. Target microservice candidates will emerge. Remember, too, that it’s better to start with a “coarse-grained” microservice and refactor back to smaller services than to start with a large group of small services. Microservice architectures, like most good architectures, are emergent and not preplanned to-the-minute.
2. _Software engineer_—The fact that the service is small doesn’t mean good design principles get thrown out the window. Focus on building a layered service where each layer in the service has discrete responsibilities. Avoid the temptation to build frameworks in your code and try to make each microservice completely independent. Premature framework design and adoption can have massive maintenance costs later in the lifecycle of the application.
3. _DevOps engineer_—Services don’t exist in a vacuum. Establish the lifecycle of your services early. The DevOps perspective needs to focus not only on how to automate the building and deployment of a service, but also on how to monitor the health of the service and react when something goes wrong. Operationalizing a service often takes more work and forethought than writing business logic.

云上的微服务看起来好像很简单。但若要成功地运转起来，我们需要结合架构师，开发人员，以及DevOps工程师地观点角度。每个观点地关键结论是

1. 架构师—架构师关注业务问题的大致轮廓，描述业务问题域，并倾听你描述的业务故事，不断构思将要构建的微服务。同样要记住的是，相比一开始就是一组小的微服务，更好的实践是，由粗粒度的微服务开始，然后重构回更细的微服务。就像大多数好的架构，微服务架构是可以不断演进的，而不是预先设定好的。
2. 软件工程师—细粒度的服务并不意味着就可以无视那些好的设计原则了。软件工程师专注于构建分层的服务，每一层都有其具体的职责。
3. DevOps工程师—微服务并不是存在于真空里的。从DevOps工程师的角度来看，他们不仅要专注于如何自动化微服务的构建和部署，而且还要专注于微服务的健康监控以及在出现问题时要如何响应。相比编写业务逻辑，微服务的运维通常需要更多的工作和前瞻性。



