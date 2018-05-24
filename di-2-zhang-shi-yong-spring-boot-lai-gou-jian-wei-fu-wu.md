# 使用Spring Boot来构建微服务

> **This chapter covers**
>
> * Learning the key characteristics of a microservice
>
> * Understanding how microservices fit into a cloud architecture
>
> * Decomposing a business domain into a set of microservices
>
> * Implementing a simple microservice using Spring Boot
>
> * Understanding the perspectives for building microservice-based applications
>
> * Learning when not to use microservices
>
> 本章包含
>
> * 学习微服务的关键特性
> * 了解微服务如何适应云架构
> * 将业务域拆解成一组微服务
> * 使用Spring Boot来实现一个简单的微服务
> * 了解构建基于微服务的应用的方方面面
> * 学习什么时候不应该使用微服务

The history of software development is littered with the tales of large development projects that after an investment of millions of dollars and hundreds of thousands of software developer hours, and with many of the best and brightest minds in the industry working on them, somehow never managed to deliver anything of value to their customers and literally collapsed under their own complexity and weight.

在软件开发的历史里，有很多大型开发项目的故事。在这些项目的背后，投入了几百万美金以及软件开发人员成百上千个小时，而且在这些人员里面还不乏行业里最优秀最聪明的头脑，但不知怎么的，总是无法向他们的客户交付任何有价值的东西，却被他们自身的复杂和笨重给压垮了。

These mammoth projects tended to follow large, traditional waterfall development methodologies that insisted that all the application’s requirements and design be defined at the beginning of the project. So much emphasis was placed on getting all the specifications for the software “correct” that there was little leeway to meet new business requirements, or refactor and learn from mistakes made in the early stages of development.

这些庞大的项目总是遵循大型传统的瀑布式开发方法，这些方法坚持所有的应用需求和设计要在项目的开始就定义好。于是，很多重点就被放到了让软件规格正确这点上来了，以致几乎没有什么余地来满足性的业务需求，或者重构并从开发的早期出现的错误中学习。

The reality, though, is that software development isn’t a linear process of definition and execution, but rather an evolutionary one where it takes several iterations of communicating with, learning from, and delivering to the customer before the development team truly understands the problem at hand.

然而，事实却是，软件开发并不是定义后就执行这么一个流水行过程，而是一个演化的过程，在开发团队真正理解手里的问题前，需要与客户进行多次沟通，学习，并交付一些东西。

Compounding the challenges of using traditional waterfall methodologies is that many times the granularity of the software artifacts being delivered in these projects are

* _Tightly coupled_—The invocation of business logic happens at the programming-language level instead of through implementation-neutral protocols such as SOAP and REST. This greatly increases the chance that even a small change to an application component can break other pieces of the application and intro- duce new bugs.

* _Leaky_—Most large software applications manage different types of data. For instance, a customer relationship management \(CRM\) application might man- age customer, sales, and product information. In a traditional model, this data is kept in the same data model and within the same data store. Even though there are obvious boundaries between the data, too often it’s tempting for a team from one domain to directly access the data that belongs to another team.  
  This easy access to data creates hidden dependencies and allows implementation details of one component’s internal data structures to leak through the entire application. Even small changes to a single database table can require a significant number of code changes and regression-testing throughout the entire application.

* _Monolithic_—Because most of the application components for a traditional appli- cation reside in a single code base that’s shared across multiple teams, any time a change to the code is made, the entire application has to be recompiled, rerun through an entire testing cycle, and redeployed. Even small changes to the application’s code base, whether they’re new customer requirements or bug fixes, become expensive and time-consuming, and large changes become nearly impossible to do in a timely fashion.

使用传统瀑布式方法的挑战是，很多时候这些项目交付的软件的粒度具有以下几个特点

* 紧耦合——

A microservice-based architecture takes a different approach to delivering functional- ity. Specifically, microservice-based architectures have these characteristics:

* _Constrained_—Microservices have a single set of responsibilities and are narrow in scope. Microservices embrace the UNIX philosophy that an application is nothing more than a collection of services where each service does one thing and does that one thing really well.

* _Loosely coupled_—A microservice-based application is a collection of small ser- vices that only interact with one another through a non–implementation spe- cific interface using a non-proprietary invocation protocol \(for example, HTTP and REST\). As long as the interface for the service doesn’t change, the owners of the microservice have more freedom to make modifications to the service than in a traditional application architecture.

* _Abstracted_—Microservices completely own their data structures and data sources. Data owned by a microservice can only be modified by that service. Access control to the database holding the microservice’s data can be locked down to only allow the service access to it.

* _Independent_—Each microservice in a microservice application can be compiled and deployed independently of the other services used in the application. This means changes can be isolated and tested much more easily than with a more heavily interdependent, monolithic application.

Why are these microservice architecture attributes important to cloud-based develop- ment? Cloud-based applications in general have the following:

* _A large and diverse user base_—Different customers want different features, and they don’t want to have to wait for a long application release cycle before they can start using these features. Microservices allow features to be delivered quickly, because each service is small in scope and accessed through a well- defined interface.

* _Extremely high uptime requirements_—Because of the decentralized nature of microservices, microservice-based applications can more easily isolate faults and problems to specific parts of an application without taking down the entire application. This reduces overall downtime for applications and makes them more resistent to problems.

* _Uneven volume requirements_—Traditional applications deployed within the four walls of a corporate data center usually have consistent usage patterns that emerge over time. This makes capacity planning for these types of applications simple. But in a cloud-based application, a simple tweet on Twitter or a post on Slashdot can drive demand for a cloud-based application through the roof.  
  Because microservice applications are broken down into small components that can be deployed independently of one another, it’s much easier to focus on the components that are under load and scale those components horizontally across multiple servers in a cloud.

This chapter provides you with the foundation you need to target and identify microservices in your business problem, build the skeleton of a microservice, and then understand the operational attributes that need to be in place for a microservice to be deployed and managed successfully in production.

To successfully design and build microservices, you need to approach microser- vices as if you’re a police detective interviewing witnesses to a crime. Even though every witness saw the same events take place, their interpretation of the crime is shaped by their background, what was important to them \(for example, what moti- vates them\), and what environmental pressures were brought to bear at that moment they witnessed the event. Participants each have their own perspectives \(and biases\) of what they consider important.

Like a successful police detective trying to get to the truth, the journey to build a suc- cessful microservice architecture involves incorporating the perspectives of multiple individuals within your software development organization. Although it takes more than technical people to deliver an entire application, I believe that the foundation for successful microservice development starts with the perspectives of three critical roles:

* _The architect_—The architect’s job is to see the big picture and understand how an application can be decomposed into individual microservices and how the microservices will interact to deliver a solution.

* _The software developer_—The software developer writes the code and understands in detail how the language and development frameworks for the language will be used to deliver a microservice.

* _The DevOps engineer_—The DevOps engineer brings intelligence to how the ser- vices are deployed and managed throughout not only production, but also all the nonproduction environments. The watchwords for the DevOps engineer are consistency and repeatability in every environment.

In this chapter, I’ll demonstrate how to design and build a set of microservices from the perspective of each of these roles using Spring Boot and Java. By the time the chapter concludes, you’ll have a service that can be packaged and deployed to the cloud.

