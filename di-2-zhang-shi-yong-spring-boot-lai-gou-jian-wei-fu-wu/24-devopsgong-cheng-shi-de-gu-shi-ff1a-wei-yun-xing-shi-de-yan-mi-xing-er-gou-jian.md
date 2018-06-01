### 2.4 DevOps工程师的故事：为运行时的严密性而构建

For the DevOps engineer, the design of the microservice is all about managing the service after it goes into production. Writing the code is often the easy part. Keeping it running is the hard part.

While DevOps is a rich and emerging IT field, you’ll start your microservice development effort with four principles and build on these principles later in the book. These principles are

1. A microservice should be self-contained and independently deployable with multiple instances of the service being started up and torn down with a single software artifact.
2. A microservice should be configurable. When a service instance starts up, it should read the data it needs to configure itself from a central location or have its configuration information passed on as environment variables. No human intervention should be required to configure the service.
3. A microservice instance needs to be transparent to the client. The client should never know the exact location of a service. Instead, a microservice client should talk to a service discovery agent that will allow the application to locate an instance of a microservice without having to know its physical location.
4. A microservice should communicate its health. This is a critical part of your cloud architecture. Microservice instances will fail and clients need to route around bad service instances.

These four principles expose the paradox that can exist with microservice development. Microservices are smaller in size and scope, but their use introduces more moving parts in an application, especially because microservices are distributed and running independently of each other in their own distributed containers. This introduces a high degree of coordination and more opportunities for failure points in the application.



