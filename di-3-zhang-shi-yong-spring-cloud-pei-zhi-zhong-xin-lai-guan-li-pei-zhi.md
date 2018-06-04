### 第3章 使用Spring Cloud配置中心来管理配置

> **This chapter covers**  
> 1. Separating service configuration from service code  
> 2. Configuring a Spring Cloud configuration server  
> 3. Integrating a Spring Boot microservice  
> 4. Encrypting sensitive properties
>
> 本章涵盖  
> 1. 将服务配置与服务代码分离  
> 2. 配置一个Spring Cloud配置中心  
> 3. 整合Spring Boot微服务  
> 4. 加密敏感配置

At one point or another, a developer will be forced to separate configuration information from their code. After all, it has been drilled into their heads since school that they shouldn’t hard-code values into the application code. Many developers will use a constants class file in their application to help centralize all their configuration in one place. Application configuration data written directly into the code is often problematic because every time a change to the configuration has to be made the application has to be recompiled and/or redeployed. To avoid this, developers will separate the configuration information from the application code completely. This makes it easy to make changes to configuration without going through a recompile process, but also introduces complexity because you now have another artifact that needs to be managed and deployed with the application.

有时候，开发人员不得不将配置信息从代码里剥离。毕竟，在学校里，他们就被灌输了“不能在应用代码里硬编码值”的思想。许多开发人员会在应用里通过一个常量类文件来帮助他们在一个地方进行配置的中心化管理。将应用的配置数据直接写入代码里总是容易出问题的，因为每次修改配置都会导致应用重新编译并且/或重新部署。为了避免这一点，开发人员需要将配置信息与应用代码完全分离。这么做可以使得当配置被修改时不用再重新编译一次，但也同样引入了一些复杂性，因为此时我们有了别的组件需要管理，并且需要把它部署进应用里。

Many developers will turn to the lowly property file \(or YAML, JSON, or XML\) to store their configuration information. This property file will sit out on a server often containing database and middleware connection information and metadata about the application that will drive the application’s behavior. Segregating your application into a property file is easy and most developers never do any more operationalization of their application configuration then placing their configuration file under source control \(if that\) and deploying it as part of their application.

许多开发人员都倾向于采用效率较低的配置文件（YAML，JSON，或者XML）来存储他们的配置信息。配置文件位于服务器里，而且通常包含着数据库和中间件的连接信息，以及驱动应用行为的元数据。将应用与配置文件隔离不难，而且多数开发人员不会对应用配置做更多的操作，如对配置文件进行源码控制（如果有的话）以及将它们作为应用的一部分进行部署。

This approach might work with a small number of applications, but it quickly falls apart when dealing with cloud-based applications that may contain hundreds of microservices, where each microservice in turn might have multiple service instances running.

这种方式对于少数的应用也许能运转，但当面对包含着数百个微服务的基于云的应用，而且每个微服务都跑着多个服务实例时，这种方式很快就崩溃了。

Suddenly configuration management becomes a big deal as application and operations team in a cloud-based environment have to wrestle with a rat’s nest of which configuration files go where. Cloud-based microservices development emphasizes

