### 1.10.5 Spring Cloud/Netflix Zuul

Spring Cloud uses the Netflix Zuul project \([https://github.com/Netflix/zuul](https://github.com/Netflix/zuul)\) to provide service routing capabilities for your microservice application. Zuul is a service gateway that proxies service requests and makes sure that all calls to your microservices go through a single “front door” before the targeted service is invoked. With this centralization of service calls, you can enforce standard service policies such as a security authorization authentication, content filtering, and routing rules.

