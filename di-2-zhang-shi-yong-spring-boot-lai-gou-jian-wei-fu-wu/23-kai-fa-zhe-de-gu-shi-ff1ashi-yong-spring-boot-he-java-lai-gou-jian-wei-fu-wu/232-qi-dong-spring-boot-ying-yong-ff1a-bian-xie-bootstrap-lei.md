### 2.3.2 启动Spring Boot应用：编写Bootstrap类

Your goal is to get a simple microservice up and running in Spring Boot and then iterate on it to deliver functionality. To this end, you need to create two classes in your licensing service microservice:

* A Spring Bootstrap class that will be used by Spring Boot to start up and initialize the application
* A Spring Controller class that will expose the HTTP endpoints that can be invoked on the microservice

As you’ll see shortly, Spring Boot uses annotations to simplify setting up and configuring the service. This becomes evident as you look at the bootstrap class in the following listing. This bootstrap class is in the src/main/java/com/thoughtmechanix/licenses/Application.java file.

我们的目标是起一个简单的微服务，并运行在Spring Boot里，然后通过迭代来持续交付功能。为了实现这点，我们需要在授权微服务里创建两个类：

* 一个Spring Bootstrap类，这个类将被Spring Boot用来启动和初始化应用
* 一个Spring Controller类，这个类将暴露微服务的一些可以被调用的HTTP端点

就像你在接下来将看到的那样，Spring Boot通过使用注解来简化服务的建立和配置过程。我们将在下面的清单的bootstrap类更清晰地感受到这点。bootstrap类位于src/main/java/com/thoughtmechanix/licenses/Application.java文件里。

Listing 2.2 Introducing the @SpringBootApplication annotation（清单2.2 @SpringBootApplication注解的介绍）

```java
package com.thoughtmechanix.licenses;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

// @SpringBootApplication注解告诉Spring Boot框架这是项目的bootstrap类
@SpringBootApplication
public class Application {
    public static void main(String[] args) {
        // 调用run方法来启动Spring Boot服务
        SpringApplication.run(Application.class, args);
    }
}
```



