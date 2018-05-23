### 1.10.9 关于服务供应

For the provisioning implementations, we’re going to make a technology shift. The Spring framework\(s\) are geared toward application development. The Spring frameworks \(including Spring Cloud\) don’t have tools for creating a “build and deployment” pipeline. To implement a “build and deployment” pipeline you’re going to use the following tools: Travis CI \(https://travis-ci.org\) for your build tool and Docker \(https://www.docker.com/\) to build the final server image containing your microservice.

To deploy your built Docker containers, we end the book with an example of how to deploy the entire application stack built throughout this book to Amazon’s cloud.



