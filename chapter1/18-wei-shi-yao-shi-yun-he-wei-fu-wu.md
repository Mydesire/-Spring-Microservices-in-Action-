### 1.8 为什么是云和微服务

One of the core concepts of a microservice-based architecture is that each service is packaged and deployed as its own discrete and independent artifact. Service instances should be brought up quickly and each instance of the service should be indistin- guishable from another.

微服务架构的一个核心概念是，将每个服务打包并部署成独立的项目。服务实例应该是可以快速被增加的，而且服务实例之间互相独立。

As a developer writing a microservice, sooner or later you’re going to have to decide whether your service is going to be deployed to one of the following:

* Physical server—While you can build and deploy your microservices to a physical machine\(s\), few organizations do this because physical servers are constrained. You can’t quickly ramp up the capacity of a physical server and it can become extremely costly to scale your microservice horizontally across multiple physical servers.

* Virtual machine images—One of the key benefits of microservices is their ability to quickly start up and shut down microservice instances in response to scalability and service failure events. Virtual machines are the heart and soul of the major cloud providers. A microservice can be packaged up in a virtual machine image and multiple instances of the service can then be quickly deployed and started in either a IaaS private or public cloud.

* Virtual container—Virtual containers are a natural extension of deploying your microservices on a virtual machine image. Rather than deploying a service to a full virtual machine, many developers deploy their services as Docker containers \(or equivalent container technology\) to the cloud. Virtual containers run inside a virtual machine; using a virtual container, you can segregate a single virtual machine into a series of self-contained processes that share the same virtual machine image.

作为一个编写微服务的开发人员，迟早你都要决定你的服务部署在哪里，有下面几种选择：

* 物理服务器——虽然你可以在物理机上构建并部署微服务，但没有几个组织会这么做，因为物理机会有一些限制。你无法快速提高物理机的容量，而且如果你想在多台物理机上进行微服务横向扩展时，这种方式会变得极其昂贵。
* 虚拟机镜像——使用微服务的一大好处是，可以通过快速启动和关闭微服务实例来响应扩展性要求和服务失败事件。虚拟机是主流云提供商的核心和灵魂。一个微服务可以在一个虚拟机里进行打包，多个服务实例可以在IaaS私有或公有云里进行快速部署。
* 虚拟容器——虚拟容器是将微服务部署在虚拟机镜像上这种方式的一种很自然的扩展。许多开发者将他们的服务部署成Docker镜像（或者类似的容器技术）到云上，而不是将服务部署到一个完整的虚拟机上。多个虚拟容器在一台虚拟机上运行；通过使用虚拟容器，你可以将单台虚拟机分离成一系列自包含的进程，这些进程共享相同的虚拟机镜像。

The advantage of cloud-based microservices centers around the concept of elasticity. Cloud service providers allow you to quickly spin up new virtual machines and containers in a matter of minutes. If your capacity needs for your services drop, you can spin down virtual servers without incurring any additional costs. Using a cloud provider to deploy your microservices gives you significantly more horizontal scalability \(adding more servers and service instances\) for your applications. Server elasticity also means that your applications can be more resilient. If one of your microservices is having problems and is falling over, spinning up new service instances can you keep your application alive long enough for your development team to gracefully resolve the issue.

基于云的微服务的优势是，它仅仅围绕着弹性的概念。云提供商允许你在几分钟内快速创建型的虚拟机和虚拟容器。如果你的服务容量需求下降了，你可以减少虚拟服务器，而且不会产生任何额外的费用。通过云提供商来部署你的微服务可为你的应用带来更多的横向扩展能力（增加更多的服务器和服务实例）。服务器具备弹性也意味着你的应用可以更有弹性。如果你其中一个微服务出现了问题并且挂了，那么启动新的服务实例能让你的应用撑过足够长的时间，知道你的研发团队最终解决这个问题。

For this book, all the microservices and corresponding service infrastructure will be deployed to an IaaS-based cloud provider using Docker containers. This is a common deployment topology used for microservices:

* Simplified infrastructure management—IaaS cloud providers give you the ability to have the most control over your services. New services can be started and stopped with simple API calls. With an IaaS cloud solution, you only pay for the infrastructure that you use.

* Massive horizontal scalability—IaaS cloud providers allow you to quickly and succinctly start one or more instances of a service. This capability means you can quickly scale services and route around misbehaving or failing servers.

* High redundancy through geographic distribution—By necessity, IaaS providers have multiple data centers. By deploying your microservices using an IaaS cloud provider, you can gain a higher level of redundancy beyond using clusters in a data center.

对于本书，所有的微服务和相应的服务基础设施都将使用Docker容器并部署在一个基于IaaS的云提供商那里。以下是微服务常用的部署拓扑：

* 简化基础设施的惯例——IaaS云提供商使你能最大限度地控制你的服务。新服务的启动和停止都可以通过简单的API调用来进行。采用IaaS云解决方案，你只需支付你用到的基础设施的费用。
* 大规模的横向扩展性——IaaS云提供商允许你快速有效启动一个或多个服务实例。这种能力意味着你可以快速扩展服务并绕过行为不当或者出现故障的服务器。
* 通过跨区域发布提高冗余度——出于需要，IaaS提供商拥有多个数据中心。通过IaaS云提供商来部署你的微服务，除了在数据中心使用集群，你还能获得高度的冗余性。

> **Why not PaaS-based microservices? 为什么不是基于PaaS的微服务？**
>
> Earlier in the chapter we discussed three types of cloud platforms \(Infrastructure as a Service, Platform as a Service, and Software as a Services\). For this book, I’ve chosen to focus specifically on building microservices using an IaaS-based approach. While certain cloud providers will let you abstract away the deployment infrastructure for your microservice, I’ve chosen to remain vendor-independent and deploy all parts of my application \(including the servers\).
>
> 在本章的前面我们讨论过三种云平台类型（基础设施即服务，平台即服务，以及软件即服务）。对于本书，我选择专注于通过使用基于IaaS的方式来构建微服务。虽然某些云提供商能让你为你的微服务抽象掉部署基础设施，但我选择保持不依赖于提供商并部署应用的所有部分（包括服务器）。
>
> For instance, Amazon, Cloud Foundry, and Heroku give you the ability to deploy your services without having to know about the underlying application container. They provide a web interface and APIs to allow you to deploy your application as a WAR or JAR file. Setting up and tuning the application server and the corresponding Java con- tainer are abstracted away from you. While this is convenient, each cloud provider’s platform has different idiosyncrasies related to its individual PaaS solution.
>
> 例如，Amazon，Cloud Foundry，以及Heroku能让你部署服务时不用知道底层的应用容器是怎样的。
>
> An IaaS approach, while more work, is portable across multiple cloud providers and allows us to reach a wider audience with our material. Personally, I’ve found that PaaS-based cloud solutions can allow you to quickly jump start your development effort, but once your application reaches enough microservices, you start to need the flexibility the IaaS style of cloud development provides.
>
> Earlier in the chapter, I mentioned new cloud computing platforms such as Function as a Service \(FaaS\) and Container as a Service \(CaaS\). If you’re not careful, FaaS- based platforms can lock your code into a cloud vendor platform because your code is deployed to a vendor-specific runtime engine. With a FaaS-based model, you might be writing your service using a general programming language \(Java, Python, JavaScript, and so on\), but you’re still tying yourself heavily to the underlying vendor APIs and runtime engine that your function will be deployed to.

The services built in this book are packaged as Docker containers. One of the reasons why I chose Docker is that as a container technology, Docker is deployable to all the major cloud providers. Later in chapter 10, I demonstrate how to package microser- vices using Docker and then deploy these containers to Amazon’s cloud platform.

