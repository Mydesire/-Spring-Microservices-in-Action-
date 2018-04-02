### 1.2 什么是Spring而且为什么它跟微服务有关

Spring has become the de facto development framework for building Java-based applications. At its core, Spring is based on the concept of dependency injection. In a normal Java application, the application is decomposed into classes where each class often has explicit linkages to other classes in the application. The linkages are the invocation of a class constructor directly in the code. Once the code is compiled, these linkage points can’t be changed.

在基于Java的应用的构建当中，Spring已经成为了事实上的开发框架。Spring的核心概念是基于依赖注入。在一个普通的Java应用中，应用被分解成了一个个的类，每个类还与别的类有显示的链接。这些链接是通过在代码中直接调用一个类的构造器而形成的。一旦代码编译好，这些链接点就不能被改变了

This is problematic in a large project because these external linkages are brittle and making a change can result in multiple downstream impacts to other code. A dependency injection framework, such as Spring, allows you to more easily manage large Java projects by externalizing the relationship between objects within your application through convention \(and annotations\) rather than those objects having hard-coded knowledge about each other. Spring sits as an intermediary between the different Java classes of your application and manages their dependencies. Spring essentially lets you assemble your code together like a set of Lego bricks that snap together.

在大型的项目中，这将会产生问题，因为这些外部的链接是很脆弱的而且做了变动还会对其它代码产生一系列的影响。

