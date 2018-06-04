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

