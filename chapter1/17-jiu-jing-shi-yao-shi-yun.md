### 1.7 究竟什么是云

The term “cloud” has become overused. Every software vendor has a cloud and everyone’s platform is cloud-enabled, but if you cut through the hype, three basic models exist in cloud-based computing. These are

* Infrastructure as a Service \(IaaS\)
* Platform as a Service \(PaaS\)
* Software as a Service \(SaaS\)

“云”这个词已经被滥用了。每个软件供应商都有一个云，每个供应商的平台都是支持云的，但如果你深入这些炒作的概念，你会发现，在基于云的计算中，有三种基本模型。它们分别是

* 基础架构即服务（Infrastructure as a Service，IaaS）
* 平台即服务（Platform as a Service，PaaS）
* 软件即服务（Software as a Service，SaaS）

To better understand these concepts, let’s map the everyday task of making a meal to the different models of cloud computing. When you want to eat a meal, you have four choices:

1. You can make the meal at home.
2. You can go to the grocery store and buy a meal pre-made that you heat up and serve.
3. You can get a meal delivered to your house.
4. You can get in the car and eat at restaurant.

为了更好地理解这几个概念，让我们来举个例子，这个例子将每天做饭这个任务与云计算的几个模型分别做了个对应。当你想吃顿饭时，你有四种选择：

1. 你可以在家里做饭。
2. 你可以去便利店里买一份提前做好了的饭菜，然后回家里加热来吃。
3. 你可以点一个外卖送到你家里。
4. 你可以开辆车去饭店里吃一顿。

![](/assets/figure1.6.png)**Figure 1.6** The different cloud computing models come down to who’s responsible for what: the cloud vendor or you.

**图1.6** 不同的云计算模型归结为谁负责什么：云供应商还是你。

Figure 1.6 shows each model.

图1.6展示了每个模型包含的内容。

The difference between these options is about who’s responsible for cooking these meals and where the meal is going to be cooked. In the on-premise model, eating a meal at home requires you to do all the work, using your own oven and ingredients already in the home. A store-bought meal is like using the Infrastructure as a Service \(IaaS\) model of computing. You’re using the store’s chef and oven to pre-bake the meal, but you’re still responsible for heating the meal and eating it at the house \(and cleaning up the dishes afterward\).

这些模型的不同之处在于，谁对做饭负责，将在哪里做饭。在第一种模式下，在家里吃需要你包揽所有的活，使用你自己的微波炉和家里的配料。从便利店里买饭类似于使用基础架构即服务（IaaS）模型的计算。你通过便利店里的厨师和微波炉先做好了饭菜，但你仍要对饭菜进行加热并且在家里进行享用（吃完后还得自己清理碗筷）。

In a Platform as a Service \(PaaS\) model you still have responsibility for the meal, but you further rely on a vendor to take care of the core tasks associated with making a meal. For example, in a PaaS model, you supply the plates and furniture, but the res- taurant owner provides the oven, ingredients, and the chef to cook them. In the Software as a Service \(SaaS\) model, you go to a restaurant where all the food is prepared for you. You eat at the restaurant and then you pay for the meal when you’re done. you also have no dishes to prepare or wash.

在平台即服务（PaaS）的模型中，你仍然需要对饭菜负责，但你可以更多地依靠提供商去为你完成做饭相关的任务。例如，在PaaS模型中，你提供碗筷和家具，但是饭馆老板提供微波炉，配料以及做饭师傅。在软件即服务（SaaS）模型中，你只需去饭馆，那里已经为你准备好了所有的饭菜。你在饭馆里吃，吃完后付钱就可以了。你也不用准备或者洗任何碗筷。

The key items at play in each of these models are ones of control: who’s responsible for maintaining the infrastructure and what are the technology choices available for building the application? In a IaaS model, the cloud vendor provides the basic infrastructure, but you’re accountable for selecting the technology and building the final solution. On the other end of the spectrum, with a SaaS model, you’re a passive consumer of the service provided by the vendor and have no input on the technology selection or any accountability to maintain the infrastructure for the application.



> **Emerging cloud platforms**
>
> I’ve documented the three core cloud platform types \(IaaS, PaaS, SaaS\) that are in use today. However, new cloud platform types are emerging. These new platforms include Functions as a Service \(FaaS\) and Container as a Service \(CaaS\). FaaS-based \([https://en.wikipedia.org/wiki/Function\_as\_a\_Service](https://en.wikipedia.org/wiki/Function_as_a_Service)\) applications use technologies like Amazon’s Lambda technologies and Google Cloud functions to build applications deployed as “serverless” chunks of code that run completely on the cloud provider’s platform computing infrastructure. With a FaaS platform, you don’t have to manage any server infrastructure and only pay for the computing cycles required to execute the function.
>
> With the Container as a Service \(CaaS\) model, developers build and deploy their microservices as portable virtual containers \(such as Docker\) to a cloud provider. Unlike an IaaS model, where you the developer have to manage the virtual machine the service is deployed to, with CaaS you’re deploying your services in a lightweight virtual container. The cloud provider runs the virtual server the container is running on as well as the provider’s comprehensive tools for building, deploying, monitoring, and scaling containers. Amazon’s Elastic Container Service \(ECS\) is an example of a CaaS-based platform. In chapter 10 of this book, we’ll see how to deploy the microservices you’ve built to Amazon ECS.
>
> It’s important to note that with both the FaaS and CaaS models of cloud computing, you can still build a microservice-based architecture. Remember, the concept of microservices revolves around building small services, with limited responsibility, using an HTTP-based interface to communicate. The emerging cloud computing plat- forms, such as FaaS and CaaS, are really about alternative infrastructure mechanisms for deploying microservices.



