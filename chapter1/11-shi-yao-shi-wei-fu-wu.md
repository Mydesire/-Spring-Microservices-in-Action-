### 1.1 什么是微服务

Before the concept of microservices evolved, most web-based applications were built using a monolithic architectural style. In a monolithic architecture, an application is delivered as a single deployable software artifact. All the UI\(user interface\), business, and database access logic are packaged together into a single application artifact and deployed to an application server.

在微服务概念形成之前，大多数web应用都是采用单体架构来构建的。在单体架构中，一个应用是作为一个可部署的软件来交付的。所有的UI（user interface，用户接口），业务逻辑和数据库访问逻辑都是包含在一个应用软件里并且部署在一个应用服务器上。

While an application might be a deployed as a single unit of work, most of the time there will be multiple development teams working on the application. Each development team will have their own discrete pieces of the application they’re responsible for and oftentimes specific customers they’re serving with their functional piece. For example, when I worked at a large financial services company, we had an in-house, custom-built customer relations management\(CRM\)application that involved the coordination of multiple teams including the UI, the customer master, the data warehouse, and the mutual funds team. Figure 1.1 illustrates the basic architecture of this application.

虽然一个应用可能是作为一个工作单元部署的，但大多数时候会有多个开发团队在合作开发这个应用。每个开发团队负责他们自己的模块，并且服务于他们负责的模块的用户。举个例子，在我之前工作过的一个大的金融服务公司里，我们曾经多团队合作开发过一个内部定制的CRM应用（customer relations management，用户关系管理）。这些团队包括UI团队，客户主团队，数仓团队以及互惠基金团队。图1.1说明了这个应用的基本体系结构。

The problem here is that as the size and complexity of the monolithic CRM application grew, the communication and coordination costs of the individual teams working on the application didn’t scale. Every time an individual team needed to make a change, the entire application had to be rebuilt, retested and redeployed.

这里的问题是，随着单体CRM应用的规模和复杂度的增长，团队间的交流和协调成本也随之增加。每次某个团队需要做出变动，整个应用就必须得重建，重测和重部署。![](/assets/屏幕快照 2018-04-02 21.51.00.png)Figure1.1 Monolithic applications force multiple development teams to artificially synchronize their delivery because their code needs to be built, tested, and deployed as an entire unit.

图1.1 单体应用强制要求不同开发团队人为地同步他们提交的代码，因为他们的代码必须作为一个整体来构建、测试和部署。

The concept of a microservice originally crept into the software development community’s consciousness around 2014 and was a direct response to many of the challenges of trying to scale both technically and organizationally large, monolithic applications. Remember, a microservice is a small, loosely coupled, distributed service. Microservices allow you to take a large application and decompose it into easy-to-manage components with narrowly defined responsibilities. Microservices help combat the traditional problems of complexity in a large code base by decomposing the large code base down into small, well-defined pieces. The key concept you need to embrace as you think about microservices is decomposing and unbundling the functionality of your applications so they’re completely independent of one another. If we take the CRM application we saw in figure 1.1 and decompose it into microservices, it might look like what’s shown in figure 1.2.

约在2014年，微服务概念引起了软件开发社区的关注，它直接对这些挑战做出了响应：试图在技术和组织上大规模扩展应用。我们要记住，一个微服务是一个小的，松耦合的，分布式的服务。微服务允许我们将一个大型应用拆分成一个个易于管理并且严格定义好了职责的组件。微服务通过将大量代码拆解成定义良好的小块，从而帮助我们克服了由于代码体量大所带来的复杂性的问题。对于微服务，我们必须要牢记的一个关键概念是，将我们的应用功能拆解，从而使得它们不会相互依赖。如果我们将图1.1的CRM应用拆解成微服务，那它将变成如图1.2所示那样。

![](/assets/屏幕快照 2018-04-02 21.56.47.png)**Figure 1.2** Using a microservice architecture our CRM application would be decomposed into a set of microservices completely independent of each other, allowing each development team to move at their own pace.

**图1.2 **使用微服务架构后，我们的CRM应用将拆解车一组完全互相独立的微服务，允许各个开发团队依据自己的节奏来进行开发。

Looking at figure 1.2, you can see that each functional team completely owns their service code and service infrastructure. They can build, deploy, and test independently of each other because their code, source control repository, and the infrastructure \(app server and database\) are now completely independent of the other parts of the application.

从图1.2中我们可以看出，每个功能团队完全拥有自己的服务代码和服务基础设施。他们能独立地构建，部署和测试，因为他们的代码，源码管理库以及基础设置（应用服务器以及数据库）都是完全独立于整体应用的其它部分。

A microservice architecture has the following characteristics:

* Application logic is broken down into small-grained components with well-defined boundaries of responsibility that coordinate to deliver a solution.

* Each component has a small domain of responsibility and is deployed completely independently of one another. Microservices should have responsibility for a single part of a business domain. Also, a microservice should be reusable across multiple applications.

* Microservices communicate based on a few basic principles \(notice I said principles, not standards\) and employ lightweight communication protocols such as HTTP and JSON\(JavaScript Object Notation\) for exchanging data between the service consumer and service provider.

* The underlying technical implementation of the service is irrelevant because the applications always communicate with a technology-neutral protocol \(JSON is the most common\). This means an application built using a microservice application could be built with multiple languages and technologies.

* Microservices—by their small, independent, and distributed nature—allow organizations to have small development teams with well-defined areas of responsibility. These teams might work toward a single goal such as delivering an application, but each team is responsible only for the services on which they’re working.

微服务体系架构有以下几点特征：

* 应用逻辑分解成几个细粒度的组件。这些组件有着良好定义的责任边界，并合作交付一个解决方案。
* 每个组件都有一个范围小的责任，并且可以独立于其它组件来进行部署。每个微服务都只对一个业务领域负责，而且一个微服务可以在多个应用上被复用。
* 微服务之间的通信基于少数几种原则（注意，我说的是原则，不是标准），并且使用轻量的通信协议（如HTTP和JSON）在服务消费者和服务提供者之间进行数据交换。
* 服务的底层技术实现是无关紧要的，因为应用之间一般都是采用技术中立的协议（JSON是最常见的协议）来进行通信。这意味着采用微服务架构的应用能通过多种语言和技术来构建。
* 微服务因其小，独立，分布式的天性，使得组织可以让一个个小团队去负责各自定义好的模块责任。这些团队也许是冲着一个目标（比如交付一个应用）而工作，但每个团队只对他们自己开发的服务负责。

I often joke with my colleagues that microservices are the gateway drug for building cloud applications. You start building microservices because they give you a high degree of flexibility and autonomy with your development teams, but you and your team quickly find that the small, independent nature of microservices makes them easily deployable to the cloud. Once the services are in the cloud, their small size makes it easy to start up large numbers of instances of the same service, and suddenly your applications become more scalable and, with forethought, more resilient.

我常常和我的同事们开玩笑说，微服务可以拿来入门构建云应用。你会去构建微服务是因为微服务能给予你高度的灵活性，并让你的开发团队们能各自管理自己，但你跟你的团队发现，微服务小而独立的天性使得他们很容易在云上部署。一旦这些服务上了云，他们的小巧使得你很容易开启相同服务的多个实例，然后突然你的应用变得更可扩展化，而且在可预见的将来变得更有弹性。

