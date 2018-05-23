### 1.10.2 Spring Cloud Config

Spring Cloud Config handles the management of application configuration data through a centralized service so your application configuration data \(particularly your environment specific configuration data\) is cleanly separated from your deployed microservice. This ensures that no matter how many microservice instances you bring up, they’ll always have the same configuration. Spring Cloud Config has its own property management repository, but also integrates with open source projects such as the following:

* _Git_—Git \([https://git-scm.com/](https://git-scm.com/\)\) is an open source version control system that allows you to manage and track changes to any type of text file. Spring Cloud Config can integrate with a Git-backed repository and read the application’s configuration data out of the repository.

* _Consul_—Consul \([https://www.consul.io/](https://www.consul.io/\)\) is an open source service discovery tool that allows service instances to register themselves with the service. Service clients can then ask Consul where the service instances are located. Consul also includes key-value store based database that can be used by Spring Cloud Config to store application configuration data.

* _Eureka_—Eureka \([https://github.com/Netflix/eureka](https://github.com/Netflix/eureka\)\) is an open source Netflix project that, like Consul, offers similar service discovery capabilities. Eureka also has a key-value database that can be used with Spring Cloud Config.

Spring Cloud Config通过中心化服务帮助我们处理了应用配置数据的管理工作，这样，应用的配置数据（尤其是特定环境的配置数据）就清晰地与你部署了的微服务分离开来了。这么做保证了无论你起了多少微服务，它们的配置都是相同的。虽然Spring Cloud Config有它自己的属性管理仓库，但也与一些开源的项目进行了集成，比如以下这些：

* Git——Git（[https://git-scm.com/](https://git-scm.com/\)）是个开源的版本控制系统，它允许你管理和追踪文本文件的任何变化。Spring Cloud Config可以跟基于Git的仓库进行集成，并从仓库里读取出应用的配置数据。
* Consul——Consul（[https://www.consul.io/](https://www.consul.io/\)）是一款开源的服务发现工具，它允许服务实例将它们自己注册到Consul服务上。然后服务客户端可以询问Consul服务实例的位置。Consul也包含了个基于键—值（key-value）的数据库，Spring Cloud Config可以用这个库来存储应用配置数据
* Eureka——Eureka（[https://github.com/Netflix/eureka](https://github.com/Netflix/eureka\)）是一个开源Netflix项目，就像Consul，它提供了类似的服务发现功能。Eureka同样包含了一个可以被Spring Cloud Config使用的键—值数据库。



