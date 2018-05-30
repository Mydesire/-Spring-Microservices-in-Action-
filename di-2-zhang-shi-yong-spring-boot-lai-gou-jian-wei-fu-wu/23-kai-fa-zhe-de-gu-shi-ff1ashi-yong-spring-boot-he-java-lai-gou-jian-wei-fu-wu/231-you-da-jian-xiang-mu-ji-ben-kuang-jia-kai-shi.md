### 2.3.1 由搭建项目基本框架开始

To begin, you’ll create a skeleton project for the licensing. You can either pull down the source code down from GitHub \([https://github.com/carnellj/spmia-chapter2](https://github.com/carnellj/spmia-chapter2)\) or create a licensing-service project directory with the following directory structure:

我们先为授权微服务搭建一个基本框架。你可以从Github（[https://github.com/carnellj/spmia-chapter2](https://github.com/carnellj/spmia-chapter2)）上拉取源代码下来，或者也可以根据下面的目录结构创建授权微服务项目目录：

* licensing-service
* src/main/java/com/thoughtmechanix/licenses
* controllers
* model
* services
* resources

Once you’ve pulled down or created this directory structure, begin by writing your Maven script for the project. This will be the pom.xml file located at the root of the project directory. The following listing shows the Maven POM file for your licensing service.

拉取完代码或者创建完目录结构后，我们就开始编写项目的Maven脚本。这个脚本就是pom.xml文件，它位于项目目录的根目录。下面是授权微服务的Mavne POM文件的内容。

Listing 2.1 Maven pom file for the licensing service（清单2.1 授权微服务的Maven pom文件）

```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.thoughtmechanix</groupId>
    <artifactId>licensing-service</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <packaging>jar</packaging>
    <name>EagleEye Licensing Service</name>
    <description>Licensing Service</description>
    <!--让Maven包含Spring Boot Starter依赖-->
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.4.4.RELEASE</version>
        <relativePath/>
    </parent>
    <dependencies>
        <!--让Maven包含Spring Boot web依赖-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <!--让Naven包含Spring Actuator依赖-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-actuator</artifactId>
        </dependency>
    </dependencies>
    <!--Note: Some the build properties and Docker build plugins have been
    excluded from the pom.xml in this pom (not in the source code in the
    github repository) because they are not relevant to our discussion here.
    注意：一些构建属性以及Docker构建插件从本pom.xml文件里排除了（本pom文件不在github代码库
    的源码里），因为它们与此处的讨论无关。
    -->
    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
</project>
```



