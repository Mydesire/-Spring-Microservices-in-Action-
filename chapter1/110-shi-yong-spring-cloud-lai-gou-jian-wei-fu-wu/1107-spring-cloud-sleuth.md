### 1.10.7 Spring Cloud Sleuth

Spring Cloud Sleuth \([https://cloud.spring.io/spring-cloud-sleuth/](https://cloud.spring.io/spring-cloud-sleuth/%29%29 allows you to integrate unique tracking identifiers into the HTTP calls and message channels %28RabbitMQ, Apache Kafka%29\\)\) being used within your application. These tracking numbers, sometimes referred to as correlation or trace ids, allow you to track a transaction as it flows across the different services in your application. With Spring Cloud Sleuth, these trace IDs are automatically added to any logging statements you make in your microservice.



The real beauty of Spring Cloud Sleuth is seen when it’s combined with logging aggregation technology tools such as Papertrail \([http://papertrailapp.com\](http://papertrailapp.com%29%29\)\) and tracing tools such as Zipkin \([http://zipkin.io\](http://zipkin.io%29%29\)\). Papertail is a cloud-based logging platform used to aggregate logs in real time from different microservices into one queryable database. Open Zipkin takes data produced by Spring Cloud Sleuth and allows you to visualize the flow of your service calls involved for a single transaction.

