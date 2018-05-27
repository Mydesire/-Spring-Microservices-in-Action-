### 2.2.4 数据传输和一致性

As you begin looking at microservices, you need to think through the data usage patterns of your services and how service consumers are going to use them. A microservice wraps around and abstracts away a small number of tables and works well as a mechanism for performing “operational” tasks such as creating, adding, and performing simple \(non-complex\) queries against a store.

当你决定用微服务时，你必须考虑服务的数据使用模式以及服务消费方将如何使用这些数据。一个微服务对数据库里的为数不多的几张表进行了包装和抽象，并通过一套机制来执行一些对应于数据库的“操作”型的任务，如创建，添加，以及一些简单的查询。

If your applications need to do complex data aggregation or transformation across multiple sources of data, the distributed nature of microservices will make this work difficult. Your microservices will invariably take on too much responsibility and can also become vulnerable to performance problems.

如果你的应用需要做一些复杂的数据符合操作或者跨多数据源的传输，那么微服务的分布式的天性可能会使得这些工作变得困难。你的微服务将总是肩负过多的责任，而且容易收到性能问题的影响。

Also keep in mind that no standard exists for performing transactions across microservices. If you need transaction management, you will need to build that logic yourself. In addition, as you’ll see in chapter 7, microservices can communicate amongst themselves by using messages. Messaging introduces latency in data updates. Your applications need to handle eventual consistency where updates that are applied to your data might not immediately appear.

还有要记住的一点是，对于跨微服务之间的事务，目前没有现存的标准。如果你需要事务管理，那么你需要自己建一套逻辑。另外，就像你将在第7章里看到的，微服务之间通过消息机制进行交流。在数据更新时，消息机制会导致延迟。你的应用需要

