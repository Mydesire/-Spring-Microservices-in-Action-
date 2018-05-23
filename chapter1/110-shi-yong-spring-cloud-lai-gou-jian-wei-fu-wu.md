### 1.10 使用Spring Cloud来构建微服务

In this section, I briefly introduce the Spring Cloud technologies that you’ll use as you build out your microservices. This is a high-level overview; when you use each technology in this book, I’ll teach you the details on each as needed.

在本节里，我将简单地介绍下构我们在建微服务时将要用到的Spring Cloud技术。这里进行的是高层次的概述，在本书将要用到每种技术时，我将对它们进行详细的介绍。

Implementing all these patterns from scratch would be a tremendous amount of work. Fortunately for us, the Spring team has integrated a wide number of battletested open source projects into a Spring subproject collectively known as Spring Cloud. \([http://projects.spring.io/spring-cloud/](http://projects.spring.io/spring-cloud/%29\)）.

从头开始实现上一节里介绍的那些模式将会是个巨大的工程量。幸运的是，Spring团队已经帮我们整合了一套经过广泛实战检验过的开源项目，并形成一个Spring子项目，它就是Spring Cloud。（[http://projects.spring.io/spring-cloud/](http://projects.spring.io/spring-cloud/%29\)）。

Spring Cloud wraps the work of open source companies such as Pivotal, HashiCorp, and Netflix in delivering patterns. Spring Cloud simplifies setting up and configuring of these projects into your Spring application so that you can focus on writing code, not getting buried in the details of configuring all the infrastructure that can go with building and deploying a microservice application.

Spring Cloud以开放的模式包装了一些开源公司（如Pivotal，HashiCorp以及Netflix）的工作成果。在你的Spring应用里，Spring Cloud帮你简化了这些项目的设置和配置，以让你可以专注于编写代码，而不用陷入构建和部署微服务应用所需的基础设施的配置细节里。

Figure 1.14 maps the patterns listed in the previous section to the Spring Cloud projects that implement them.

图1.14对上一节里列出的模式与Spring Cloud项目对这些模式的实现做了个对应。

Let’s walk through these technologies in greater detail.

接下来让我们详细看看这些技术。![](/assets/figure1.14.png)**Figure 1.14** You can map the technologies you’re going to use directly to the microservice patterns we’ve explored so far in this chapter.

图1.14 你可以直接把这些即将用到的技术与我们到目前为止探索过的模式做个映射。

