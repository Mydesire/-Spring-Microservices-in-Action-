### 1.8 为什么是云和微服务

One of the core concepts of a microservice-based architecture is that each service is packaged and deployed as its own discrete and independent artifact. Service instances should be brought up quickly and each instance of the service should be indistin- guishable from another.

As a developer writing a microservice, sooner or later you’re going to have to decide whether your service is going to be deployed to one of the following:

*  Physical server—While you can build and deploy your microservices to a physi- cal machine\(s\), few organizations do this because physical servers are con- strained. You can’t quickly ramp up the capacity of a physical server and it can become extremely costly to scale your microservice horizontally across multiple physical servers.

* Virtual machine images—One of the key benefits of microservices is their ability to quickly start up and shut down microservice instances in response to scalability and service failure events. Virtual machines are the heart and soul of the major cloud providers. A microservice can be packaged up in a virtual machine image and multiple instances of the service can then be quickly deployed and started in either a IaaS private or public cloud.

* Virtual container—Virtual containers are a natural extension of deploying your microservices on a virtual machine image. Rather than deploying a service to a full virtual machine, many developers deploy their services as Docker contain- ers \(or equivalent container technology\) to the cloud. Virtual containers run inside a virtual machine; using a virtual container, you can segregate a single virtual machine into a series of self-contained processes that share the same virtual machine image.

The advantage of cloud-based microservices centers around the concept of elasticity. Cloud service providers allow you to quickly spin up new virtual machines and contain- ers in a matter of minutes. If your capacity needs for your services drop, you can spin down virtual servers without incurring any additional costs. Using a cloud provider to deploy your microservices gives you significantly more horizontal scalability \(adding more servers and service instances\) for your applications. Server elasticity also means that your applications can be more resilient. If one of your microservices is having prob- lems and is falling over, spinning up new service instances can you keep your applica- tion alive long enough for your development team to gracefully resolve the issue.

For this book, all the microservices and corresponding service infrastructure will be deployed to an IaaS-based cloud provider using Docker containers. This is a common deployment topology used for microservices:

* Simplified infrastructure management—IaaS cloud providers give you the ability to have the most control over your services. New services can be started and stopped with simple API calls. With an IaaS cloud solution, you only pay for the infrastructure that you use.

* Massive horizontal scalability—IaaS cloud providers allow you to quickly and succinctly start one or more instances of a service. This capability means you can quickly scale services and route around misbehaving or failing servers.

* High redundancy through geographic distribution—By necessity, IaaS providers have multiple data centers. By deploying your microservices using an IaaS cloud provider, you can gain a higher level of redundancy beyond using clusters in a data center.

> **Why not PaaS-based microservices?**
>
> Earlier in the chapter we discussed three types of cloud platforms \(Infrastructure as a Service, Platform as a Service, and Software as a Services\). For this book, I’ve cho- sen to focus specifically on building microservices using an IaaS-based approach. While certain cloud providers will let you abstract away the deployment infrastructure for your microservice, I’ve chosen to remain vendor-independent and deploy all parts of my application \(including the servers\).
>
> For instance, Amazon, Cloud Foundry, and Heroku give you the ability to deploy your services without having to know about the underlying application container. They pro- vide a web interface and APIs to allow you to deploy your application as a WAR or JAR file. Setting up and tuning the application server and the corresponding Java con- tainer are abstracted away from you. While this is convenient, each cloud provider’s platform has different idiosyncrasies related to its individual PaaS solution.
>
> An IaaS approach, while more work, is portable across multiple cloud providers and allows us to reach a wider audience with our material. Personally, I’ve found that PaaS-based cloud solutions can allow you to quickly jump start your development effort, but once your application reaches enough microservices, you start to need the flexibility the IaaS style of cloud development provides.
>
> Earlier in the chapter, I mentioned new cloud computing platforms such as Function as a Service \(FaaS\) and Container as a Service \(CaaS\). If you’re not careful, FaaS- based platforms can lock your code into a cloud vendor platform because your code is deployed to a vendor-specific runtime engine. With a FaaS-based model, you might be writing your service using a general programming language \(Java, Python, JavaScript, and so on\), but you’re still tying yourself heavily to the underlying vendor APIs and runtime engine that your function will be deployed to.

The services built in this book are packaged as Docker containers. One of the reasons why I chose Docker is that as a container technology, Docker is deployable to all the major cloud providers. Later in chapter 10, I demonstrate how to package microser- vices using Docker and then deploy these containers to Amazon’s cloud platform.

