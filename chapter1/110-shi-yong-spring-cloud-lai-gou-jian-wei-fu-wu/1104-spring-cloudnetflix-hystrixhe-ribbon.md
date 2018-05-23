### 1.10.4 Spring Cloud/Netflix Hystrix和Ribbon

Spring Cloud heavily integrates with Netflix open source projects. For microservice client resiliency patterns, Spring Cloud wraps the Netflix Hystrix libraries \([https://github.com/Netflix/Hystrix](https://github.com/Netflix/Hystrix\)\) and Ribbon project \([https://github.com/Netflix/Ribbon](https://github.com/Netflix/Ribbon\)\) and makes using them from within your own microservices trivial to implement.

Using the Netflix Hystrix libraries, you can quickly implement service client resiliency patterns such as the circuit breaker and bulkhead patterns.

While the Netflix Ribbon project simplifies integrating with service discovery agents such as Eureka, it also provides client-side load-balancing of service calls from a service consumer. This makes it possible for a client to continue making service calls even if the service discovery agent is temporarily unavailable.

