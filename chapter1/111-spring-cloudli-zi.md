### 1.11 Spring Cloud例子

In the last section, we walked through all the different Spring Cloud technologies that you’re going to use as you build out your microservices. Because each of these technologies are independent services, it’s obviously going to take more than one chapter to explain all of them in detail. However, as I wrap up this chapter, I want to leave you with a small code example that again demonstrates how easy it is to integrate these technologies into your own microservice development effort.

Unlike the first code example in listing 1.1, you can’t run this code example because a number of supporting services need to be set up and configured to be used. Don’t worry, though; the setup costs for these Spring Cloud services \(configuration service, service discovery\) are a one-time cost in terms of setting up the service. Once they’re set up, your individual microservices can use these capabilities over and over again. We couldn’t fit all that goodness into a single code example at the beginning of  
 the book.

The code shown in the following listing quickly demonstrates how the service discovery, circuit breaker, bulkhead, and client-side load balancing of remote services were integrated into our “Hello World” example.

```java
// Listing 1.2 Hello World Service using Spring Cloud
//Removed other imports for conciseness
import com.netflix.hystrix.contrib.javanica.annotation.HystrixCommand;
import com.netflix.hystrix.contrib.javanica.annotation.HystrixProperty;
import org.springframework.cloud.netflix.eureka.EnableEurekaClient;
import org.springframework.cloud.client.circuitbreaker.EnableCircuitBreaker;
@SpringBootApplication
@RestController
@RequestMapping(value="hello")
@EnableCircuitBreaker
@EnableEurekaClient
public class Application {
	public static void main(String[] args) {
		SpringApplication.run(Application.class, args);
	}
	@HystrixCommand(threadPoolKey = "helloThreadPool")
	public String helloRemoteServiceCall(String firstName, String lastName){
		ResponseEntity<String> restExchange = restTemplate.exchange("http://logical-service-id/name/[ca]{firstName}/{lastName}", HttpMethod.GET, null, String.class, firstName, lastName);
		return restExchange.getBody();
	}
	@RequestMapping(value="/{firstName}/{lastName}", method = RequestMethod.GET)
	public String hello( @PathVariable("firstName") String firstName, @PathVariable("lastName") String lastName) {
		return helloRemoteServiceCall(firstName, lastName)
	}
}
```

This code has a lot packed into it, so let’s walk through it. Keep in mind that this listing is only an example and isn’t found in the chapter 1 GitHub repository source code. I’ve included it here to give you a taste of what’s to come later in the book.

The first thing you should notice is the @EnableCircuitBreaker and @EnableEurekaClient annotations. The @EnableCircuitBreaker annotation tells your Spring microservice that you’re going to use the Netflix Hystrix libraries in your application. The @EnableEurekaClient annotation tells your microservice to register itself with a Eureka Service Discovery agent and that you’re going to use service discovery to look up remote REST services endpoints in your code. Note that configuration is happening in a property file that will tell the simple service the location and port number of a Eureka server to contact. You first see Hystrix being used when you declare your hello method:

```java
@HystrixCommand(threadPoolKey = "helloThreadPool")
public String helloRemoteServiceCall(String firstName, String lastName)
```

The @HystrixCommand annotation is doing two things. First, any time the helloRemoteServiceCall method is called, it won’t be directly invoked. Instead, the method will be delegated to a thread pool managed by Hystrix. If the call takes too long \(default is one second\), Hystrix steps in and interrupts the call. This is the implementation of the circuit breaker pattern. The second thing this annotation does is create a thread pool called helloThreadPool that’s managed by Hystrix. All calls to helloRemoteServiceCall method will only occur on this thread pool and will be isolated from any other remote service calls being made.

The last thing to note is what’s occurring inside the helloRemoteServiceCall method. The presence of the @EnableEurekaClient has told Spring Boot that you’re going to use a modified RestTemplate class \(this isn’t how the Standard Spring RestTemplate would work out of the box\) whenever you make a REST service call. This RestTemplate class will allow you to pass in a logical service ID for the service you’re trying to invoke: 

```java
ResponseEntity<String> restExchange = restTemplate.exchange (http://logical-service-id/name/{firstName}/{lastName}
```

Under the covers, the RestTemplate class will contact the Eureka service and look up the physical location of one or more of the “name” service instances. As a consumer of the service, your code never has to know where that service is located.

Also, the RestTemplate class is using Netflix’s Ribbon library. Ribbon will retrieve a list of all the physical endpoints associated with a service. Every time the service is called by the client, it “round-robins” the call to the different service instances on the client without having to go through a centralized load balancer. By eliminating a centralized load balancer and moving it to the client, you eliminate another failure point \(load balancer going down\) in your application infrastructure.

I hope that at this point you’re impressed, because you’ve added a significant number of capabilities to your microservice with only a few annotations. That’s the real beauty behind Spring Cloud. You as a developer get to take advantage of battle-hardened microservice capabilities from premier cloud companies like Netflix and Consul. These capabilities, if used outside of Spring Cloud, can be complex and obtuse to set up. Spring Cloud simplifies their use to literally nothing more than a few simple Spring Cloud annotations and configuration entries.

