### 1.10.2 Spring Cloud Config

Spring Cloud Config handles the management of application configuration data through a centralized service so your application configuration data \(particularly your environment specific configuration data\) is cleanly separated from your deployed microservice. This ensures that no matter how many microservice instances you bring up, they’ll always have the same configuration. Spring Cloud Config has its own property management repository, but also integrates with open source projects such as the following:

* _Git_—Git \(https://git-scm.com/\) is an open source version control system that allows you to manage and track changes to any type of text file. Spring Cloud Config can integrate with a Git-backed repository and read the application’s configuration data out of the repository.

* _Consul_—Consul \(https://www.consul.io/\) is an open source service discovery tool that allows service instances to register themselves with the service. Service clients can then ask Consul where the service instances are located. Consul also includes key-value store based database that can be used by Spring Cloud Config to store application configuration data.

* _Eureka_—Eureka \(https://github.com/Netflix/eureka\) is an open source Netflix project that, like Consul, offers similar service discovery capabilities. Eureka also has a key-value database that can be used with Spring Cloud Config.



