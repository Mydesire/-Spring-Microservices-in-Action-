### 1.11 Spring Cloud例子

In the last section, we walked through all the different Spring Cloud technologies that you’re going to use as you build out your microservices. Because each of these technologies are independent services, it’s obviously going to take more than one chapter to explain all of them in detail. However, as I wrap up this chapter, I want to leave you with a small code example that again demonstrates how easy it is to integrate these technologies into your own microservice development effort.

Unlike the first code example in listing 1.1, you can’t run this code example because a number of supporting services need to be set up and configured to be used. Don’t worry, though; the setup costs for these Spring Cloud services \(configuration service, service discovery\) are a one-time cost in terms of setting up the service. Once they’re set up, your individual microservices can use these capabilities over and over again. We couldn’t fit all that goodness into a single code example at the beginning of the book.

The code shown in the following listing quickly demonstrates how the service discovery, circuit breaker, bulkhead, and client-side load balancing of remote services were integrated into our “Hello World” example.

