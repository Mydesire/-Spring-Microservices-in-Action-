### 1.10.4 Spring Cloud/Netflix Hystrix和Ribbon

Spring Cloud heavily integrates with Netflix open source projects. For microservice client resiliency patterns, Spring Cloud wraps the Netflix Hystrix libraries \([https://github.com/Netflix/Hystrix\](https://github.com/Netflix/Hystrix%29\) and Ribbon project \([https://github.com/Netflix/Ribbon\](https://github.com/Netflix/Ribbon%29\) and makes using them from within your own microservices trivial to implement.

Spring Cloud与Netflix开源项目进行了深度整合。对于微服务弹性模式，Spring Cloud包装了Netflix的Hystrix库（[https://github.com/Netflix/Hystrix](https://github.com/Netflix/Hystrix\)）以及Ribbon项目（[https://github.com/Netflix/Ribbon](https://github.com/Netflix/Ribbon\)），

Using the Netflix Hystrix libraries, you can quickly implement service client resiliency patterns such as the circuit breaker and bulkhead patterns.

通过使用Netflix的Hystrix库，你可以快速实现服务客户端弹性模式，如断路器和舱壁模式。

While the Netflix Ribbon project simplifies integrating with service discovery agents such as Eureka, it also provides client-side load-balancing of service calls from a service consumer. This makes it possible for a client to continue making service calls even if the service discovery agent is temporarily unavailable.

