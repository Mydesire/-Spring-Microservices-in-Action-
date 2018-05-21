### 1.6 为什么要改变我们构建应用的方式

We’re at an inflection point in history. Almost all aspects of modern society are now wired together via the internet. Companies that used to serve local markets are suddenly finding that they can reach out to a global customer base. However, with a larger global customer base also comes global competition. These competitive pressures mean the following forces are impacting the way developers have to think about building applications:

* _Complexity has gone way up_—Customers expect that all parts of an organization know who they are. “Siloed” applications that talk to a single database and don’t integrate with other applications are no longer the norm. Today’s applications need to talk to multiple services and databases residing not only inside a company’s data center, but also to external service providers over the internet.
* _Customers want faster delivery_—Customers no longer want to wait for the next annual release or version of a software package. Instead, they expect the features in a software product to be unbundled so that new functionality can be released quickly in weeks \(even days\) without having to wait for an entire product release.
* _Performance and scalability_—Global applications make it extremely difficult to predict how much transaction volume is going to be handled by an application and when that transaction volume is going to hit. Applications need to scale up across multiple servers quickly and then scale back down when the volume needs have passed.
* _Customers expect their applications to be available_—Because customers are one click away from a competitor, a company’s applications must be highly resilient. Failures or problems in one part of the application shouldn’t bring down the entire application.

我们正处于历史的拐点。现代社会的方方面面几乎都与互联网密不可分。原本只服务于当地市场的公司突然发现他们接触到全球的客户群。然而，在接触到全球客户群的同时，也带来了全球性的竞争。这些竞争压力意味着，开发者在考虑开发应用时受着以下几点影响：

* 
To meet these expectations, we, as application developers, have to embrace the paradox that to build high-scalable and highly redundant applications we need to break our applications into small services that can be built and deployed independently of one another. If we “unbundle” our applications into small services and move them away from a single monolithic artifact, we can build systems that are

* _Flexible_—Decoupled services can be composed and rearranged to quickly deliver new functionality. The smaller the unit of code that one is working with, the less complicated it is to change the code and the less time it takes to test deploy the code.
* _Resilient_—Decoupled services mean an application is no longer a single “ball of mud” where a degradation in one part of the application causes the whole application to fail. Failures can be localized to a small part of the application and contained before the entire application experiences an outage. This also enables the applications to degrade gracefully in case of an unrecoverable error.
* _Scalable_—Decoupled services can easily be distributed horizontally across multiple servers, making it possible to scale the features/services appropriately. With a monolithic application where all the logic for the application is intertwined, the entire application needs to scale even if only a small part of the application is the bottleneck. Scaling on small services is localized and much more costeffective.

To this end, as we begin our discussion of microservices keep the following in mind:

_Small, Simple, and Decoupled Services = Scalable, Resilient, and Flexible Applications_

