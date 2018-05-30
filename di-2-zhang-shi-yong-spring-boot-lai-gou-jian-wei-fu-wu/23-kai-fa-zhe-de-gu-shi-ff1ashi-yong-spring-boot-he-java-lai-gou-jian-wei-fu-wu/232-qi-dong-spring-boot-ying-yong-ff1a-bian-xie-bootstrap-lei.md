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

The first thing to note in this code is the use of the @SpringBootApplication annotation. Spring Boot uses this annotation to tell the Spring container that this class is the source of bean definitions for use in Spring. In a Spring Boot application, you can define Spring Beans by

1. Annotating a Java class with a @Component, @Service or @Repository annotation tag
2. Annotating a class with a @Configuration tag and then defining a constructor method for each Spring Bean you want to build with a @Bean tag.

在上面的代码里，我们首先注意到的是@SpringBootApplication注解。Spring Boot用这个注解来告诉Spring容器该类是Spring要用到的bean的定义的源头。在一个Spring Boot应用里，我们可以通过以下两种方式来定义Spring Bean

1. 用@Component，@Service或@Repository注解标签来注解一个Java类
2. 用@Configuration标签来注解一个类，然后用@Bean标签为每一个你想要构建的Spring Bean定义一个构造方法

Under the covers, the @SpringBootApplication annotation marks the Application class in listing 2.2 as a configuration class, then begins auto-scanning all the classes on the Java class path for other Spring Beans.

在上面的例子中，@SpringBootApplication注解将清单2.2里的Application类标记为一个配置类，然后开始在该类的路径下为其它的Spring Bean自动扫描所有的类。

The second thing to note is the Application class’s main\(\) method. In the main\(\) method, the SpringApplication.run\(Application.class, args\), the call starts the Spring container and returns a Spring ApplicationContext object. \(You aren’t doing anything with the ApplicationContext, so it isn’t shown in the code.\)

第二个值得注意的地方是Application类的main\(\)方法。在main\(\)方法里，通过调用SpringApplication.run\(Application.class, args\)来启动Spring容器，并且run方法会返回一个Spring ApplicationContext对象。（我们将不对ApplicationContext做任何处理，所以代码里没有展示它。）

The easiest thing to remember about the @SpringBootApplication annotation and the corresponding Application class is that it’s the bootstrap class for the entire microservice. Core initialization logic for the service should be placed in this class.

关于@SpringBootApplication注解以及对应的Application类，需要记住的是，它是整个微服务的bootstrap类。服务的核心初始化逻辑应该要放在这个类里。

