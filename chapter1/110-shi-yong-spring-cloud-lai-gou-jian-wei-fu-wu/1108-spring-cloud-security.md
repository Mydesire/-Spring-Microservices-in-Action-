### 1.10.8 Spring Cloud Security

Spring Cloud Security \([https://cloud.spring.io/spring-cloud-security/\](https://cloud.spring.io/spring-cloud-security/%29\) is an authentication and authorization framework that can control who can access your services and what they can do with your services. Spring Cloud Security is token-based and allows services to communicate with one another through a token issued by an authentication server. Each service receiving a call can check the provided token in the HTTP call to validate the user’s identity and their access rights with the service.

Spring Cloud Security（[https://cloud.spring.io/spring-cloud-security/](https://cloud.spring.io/spring-cloud-security/\)）是一个认证和授权的框架，它可以用来控制谁可以访问你的服务以及访问者可以对你的服务做什么操作。Spring Cloud Security基于令牌（token），而且允许服务通过认证服务器签署的令牌与其它服务进行交互。每个收到请求的服务可以校验在HTTP里提供的token来验证用户的身份以及他们对服务的访问权限。

In addition, Spring Cloud Security supports the JavaScript Web Token \([https://jwt.io\](https://jwt.io%29%29. The JavaScript Web Token %28JWT\)\) framework standardizes the format of how a OAuth2 token is created and provides standards for digitally signing a created token.

另外，Spring Cloud Security支持JavaScript Web令牌（[https://jwt.io](https://jwt.io%29%29. The JavaScript Web Token %28JWT\)）框架来标准化OAuth2令牌的创建方式，并为数字令牌签名提供标准。

