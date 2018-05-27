### 2.2.4 数据传输和一致性

As you begin looking at microservices, you need to think through the data usage patterns of your services and how service consumers are going to use them. A microservice wraps around and abstracts away a small number of tables and works well as a mechanism for performing “operational” tasks such as creating, adding, and performing simple \(non-complex\) queries against a store.

当你决定用微服务时，你必须考虑服务的数据使用模式以及服务消费方将如何使用这些数据。一个微服务对数据库里的为数不多的几张表进行了包装和抽象，并通过一套机制来执行一些对应于数据库的“操作”型的任务，如创建，添加，以及一些简单的查询。

If your applications need to do complex data aggregation or transformation across multiple sources of data, the distributed nature of microservices will make this work difficult. Your microservices will invariably take on too much responsibility and can also become vulnerable to performance problems.



Also keep in mind that no standard exists for performing transactions across microservices. If you need transaction management, you will need to build that logic yourself. In addition, as you’ll see in chapter 7, microservices can communicate amongst themselves by using messages. Messaging introduces latency in data updates. Your applications need to handle eventual consistency where updates that are applied to your data might not immediately appear.

