### 1.10.3 Spring Cloud service discovery

With Spring Cloud service discovery, you can abstract away the physical location \(IP and/or server name\) of where your servers are deployed from the clients consuming the service. Service consumers invoke business logic for the servers through a logical name rather than a physical location. Spring Cloud service discovery also handles the registration and deregistration of services instances as they’re started up and shut down. Spring Cloud service discovery can be implemented using Consul \(https://www.consul.io/\) and Eureka \(https://github.com/Netflix/eureka\) as its service discovery engine.

通过Spring Cloud服务发现，你可以将服务部署的物理位置（IP和/或服务名称）与服务的消费方进行抽象隔离。服务消费方通过逻辑名字来调用业务逻辑，而不是物理位置。



