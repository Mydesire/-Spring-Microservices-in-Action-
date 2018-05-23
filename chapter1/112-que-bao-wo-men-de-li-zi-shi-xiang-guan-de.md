### 1.12 确保我们的例子是相关的

I want to make sure this book provides examples that you can relate to as you go about your day-to-day job. To this end, I’ve structured the chapters in this book and the corresponding code examples around the adventures \(misadventures\) of a fictitious company called ThoughtMechanix. ThoughtMechanix is a software development company whose core product, EagleEye, provides an enterprise-grade software asset management application. It provides coverage for all the critical elements: inventory, software delivery, license management, compliance, cost, and resource management. Its primary goal is to enable organizations to gain an accurate point-in-time picture of its software assets.

The company is approximately 10 years old. While they’ve experienced solid revenue growth, internally they’re debating whether they should be re-platforming their core product from a monolithic on-premise-based application or move their application to the cloud. The re-platforming involved with EagleEye can be a “make or break” moment for a company.

The company is looking at rebuilding their core product EagleEye on a new architecture. While much of the business logic for the application will remain in place, the application itself will be broken down from a monolithic design to a much smaller microservice design whose pieces can be deployed independently to the cloud. The examples in this book won’t build the entire ThoughtMechanix application. Instead you’ll build specific microservices from the problem domain at hand and then build the infrastructure that will support these services using various Spring Cloud \(and some non-Spring-Cloud\) technologies.

The ability to successfully adopt cloud-based, microservice architecture will impact all parts of a technical organization. This includes the architecture, engineering, testing, and operations teams. Input will be needed from each group and, in the end, they’re probably going to need reorganization as the team reevaluates their responsibilities in this new environment. Let’s start our journey with ThoughtMechanix as you begin the fundamental work of identifying and building out several of the microservices used in EagleEye and then building these services using Spring Boot.



