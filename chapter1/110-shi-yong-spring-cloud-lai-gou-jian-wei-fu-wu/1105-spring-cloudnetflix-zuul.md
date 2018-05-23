### 1.10.5 Spring Cloud/Netflix Zuul

Spring Cloud uses the Netflix Zuul project \([https://github.com/Netflix/zuul](https://github.com/Netflix/zuul)\) to provide service routing capabilities for your microservice application. Zuul is a service gateway that proxies service requests and makes sure that all calls to your microservices go through a single “front door” before the targeted service is invoked. With this centralization of service calls, you can enforce standard service policies such as a security authorization authentication, content filtering, and routing rules.

Spring Cloud采用Netflix的Zuul项目（[https://github.com/Netflix/zuul](https://github.com/Netflix/zuul)）来为微服务应用提供路由功能。Zuul是一个服务网关，它代理了服务请求，保证所有对微服务发起的请求在目标服务被调用之前都要先经过单一的“前门”。通过这种中心化的服务请求，你可以实施标准的服务政策，如安全授权认证，内容过滤，以及路由规则。

