### 1.10.9 关于服务供应

For the provisioning implementations, we’re going to make a technology shift. The Spring framework\(s\) are geared toward application development. The Spring frameworks \(including Spring Cloud\) don’t have tools for creating a “build and deployment” pipeline. To implement a “build and deployment” pipeline you’re going to use the following tools: Travis CI \([https://travis-ci.org\](https://travis-ci.org\)\) for your build tool and Docker \([https://www.docker.com/\](https://www.docker.com/\)\) to build the final server image containing your microservice.

对于服务供应的实现，我们将采用不同的技术。Spring框架主要是面向应用开发。Spring框架（包括Spring Cloud）没有可以创建“构建和部署”管道的工具。为了实现一个“构建和部署”管道，我们将采用以下这些工具：构建工具用Travis CI（[https://travis-ci.org](https://travis-ci.org\)），构建最终的包含了微服务的服务器镜像用Docker（[https://www.docker.com/](https://www.docker.com/\)）。

To deploy your built Docker containers, we end the book with an example of how to deploy the entire application stack built throughout this book to Amazon’s cloud.

为了部署构建好的Docker容器，在本书的末尾我们将用一个例子来展示如何将本书的整个应用栈部署到亚马逊云。

