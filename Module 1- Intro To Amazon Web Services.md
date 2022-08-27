2/12/22

# Module 1 introduction

## **Learning objectives**

In this module, you will learn how to:

- Summarize the benefits of AWS.
- Describe differences between on-demand delivery and cloud deployments.
- Summarize the pay-as-you-go pricing model.





**AWS offers a massive range of services for every business**, starting with ==basic elements==, like **compute**, **storage**, and **network security tools**, through ==complex solutions== like **blockchain**, **machine learning,** or **artificial intelligence**, and **robot development** platforms, all the way through very ==specialized tool sets==, like **video production management** systems, and **orbital satellites you can rent** by the minute.



Almost all modern computing centers around a **basic client-server model**

![image-20220212212918899](../assets/image-20220212212918899.png)

**==Server in AWS: Amazon Elastic Compute Cloud (Amazon EC2) instance==**

- a virtual server

AWS - ==**You only pay for what you use**== - you don't prepay for anything and you don't have to worry about capacity constraints

## What is a client-server model?

You just learned more about AWS and how almost all of modern computing uses a basic client-server model. Let’s recap what a client-server model is.

![A transaction between a client and a server](../assets/8ZveG_XzU1DA7Rfl_9IKv5QPQn9lb0_BD.png)

==In computing, a **client** can be a web browser or desktop application that a person interacts with to make requests to computer servers. A **server** can be services such as Amazon Elastic Compute Cloud (Amazon EC2), a type of virtual server.==

For example, suppose that a client makes a request for a news article, the score in an online game, or a funny video. The server evaluates the details of this request and fulfills it by returning the information to the client.

## Cloud Computing

==Cloud computing is the on-demand delivery of IT resources over the internet with pay-as-you-go pricing.==

At AWS, we call that the **undifferentiated heavy lifting of IT.** Tasks that are common, often repetitive and ultimately time-consuming; these are the tasks AWS wants to help you with. So you can focus on what makes you unique

### Deployment models for cloud computing

When selecting a cloud strategy, a company must consider factors such as required <u>cloud application components</u>, <u>preferred resource management tools,</u> and <u>any legacy IT infrastructure requirements</u>.

==The three cloud computing deployment models are cloud-based, on-premises, and hybrid==



#### Cloud-based development

- <u>Run</u> all parts of the application in the cloud.
- <u>Migrate</u> existing applications to the cloud.
- <u>Design and build new applications</u> in the cloud.

==In a **cloud-based deployment** model, you can migrate existing applications to the cloud, or you can design and build new applications in the cloud.== <u>You can build those applications on low-level infrastructure</u> that requires your IT staff to manage them. A<u>lternatively, you can build them using higher-level services</u> that reduce the management, architecting, and scaling requirements of the core infrastructure.



For example, a company might create an application consisting of virtual servers, databases, and networking components that are fully based in the cloud.

### On-Premises Deployment

- <u>Deploy</u> resources by <u>using virtualization and resource management tools</u>.
- <u>Increase resource utilization</u> by using application management and virtualization technologies.

**==On-premises deployment==** is also known as a <u>*private cloud* deployment</u>. In this model, ==resources are deployed on premises by using virtualization and resource management tools==.



For example, you might have applications that run on technology that is fully kept in your on-premises data center. Though this model is much like legacy IT infrastructure, its incorporation of application management and virtualization technologies helps to increase resource utilization.

#### Hybrid Deployment

- Connect cloud-based resources to on-premises infrastructure.
- Integrate cloud-based resources with legacy IT applications.

==In a **hybrid deployment**, cloud-based resources are connected to on-premises infrastructure.== You might want to use this approach in a number of situations. For example, you have legacy applications that are better maintained on premises, or government regulations require your business to keep certain records on premises.



For example, suppose that a company wants to use cloud services that can automate batch data processing and analytics. However, the company has several legacy applications that are more suitable on premises and will not be migrated to the cloud. With a hybrid deployment, the company would be able to keep the legacy applications on premises while benefiting from the data and analytics services that run in the cloud.

## Benefits of Cloud Computing

- **Trade upfront expense for variable expense**

Upfront expense refers to data centers, physical servers, and other resources that you would need to invest in before using them. ==<u>Variable expense means you only pay for computing resources you consume</u>== instead of investing heavily in data centers and servers before you know how you’re going to use them.



By taking a cloud computing approach that offers the benefit of variable expense, companies can implement innovative solutions while saving on costs.

- **Stop spending money to run and maintain data centers**

–

Computing in data centers often requires you to spend more money and <u>time managing infrastructure and servers.</u> 



A benefit of cloud computing is the ability to <u>focus less on these tasks and more on your applications and customers</u>.

- **Stop guessing capacity**

–

With cloud computing, you don’t have to predict how much infrastructure capacity you will need before deploying an application. 



For example, <u>you can launch Amazon EC2 instances when needed, and pay only for the compute time you use</u>. Instead of paying for unused resources or having to deal with limited capacity, you can access only the capacity that you need. You can also scale in or scale out in response to demand.

- **Benefit from massive economies of scale**

–

By using cloud computing, you can achieve a lower variable cost than you can get on your own.

 

<u>Because usage from hundreds of thousands of customers can aggregate in the cloud, providers, such as AWS, can achieve higher economies of scale.</u> The economy of scale translates into lower pay-as-you-go prices. 

- **Increase speed and agility**

–

The flexibility of cloud computing makes it easier for you to develop and deploy applications.



This flexibility provides you with more time to experiment and innovate. When computing in data centers, it may take weeks to obtain new resources that you need. By comparison, <u>cloud computing enables you to access new resources within minutes</u>.

- **Go global in minutes**

–

The global footprint of the AWS Cloud enables you to deploy applications to customers around the world quickly, while providing them with low latency. This means that even if you are located in a different part of the world than your customers, customers are able to access your applications with minimal delays. 



Later in this course, you will explore the AWS global infrastructure in greater detail. You will examine some of the services that you can use to deliver content to customers around the world.

## Additional resources

To learn more about the concepts that were explored in Module 1, review these resources.

- [AWS glossary](https://docs.aws.amazon.com/general/latest/gr/glos-chap.html)
- [Whitepaper: Overview of Amazon Web Services](https://d0.awsstatic.com/whitepapers/aws-overview.pdf)
- [AWS Fundamentals: Overview](https://aws.amazon.com/getting-started/fundamentals-overview/)[
  ](https://aws.amazon.com/what-is-cloud-computing/)
- [What is cloud computing?](https://aws.amazon.com/what-is-cloud-computing/)
- [Types of cloud computing](https://aws.amazon.com/types-of-cloud-computing/)
- [Cloud computing with AWS](https://aws.amazon.com/what-is-aws/)



---

## Module 1 Quiz

<u>What is cloud computing?</u>

The correct response option is **On-demand delivery of IT resources and applications through the internet with pay-as-you-go pricing**.

 

The other response options are incorrect because:

- It is possible to back up files to the cloud, but this response option does not describe cloud computing as a whole.
- Deploying applications connected to on-premises infrastructure is a sample use case for a hybrid cloud deployment. Remember that cloud computing also has cloud and on-premises (or private cloud) deployment models.
- AWS Lambda is an AWS service that lets you run code without needing to manage or provision servers. This description does not describe cloud computing as a whole. AWS Lambda is explained in greater detail later in the course.





<u>What is another name for on-premises deployment?</u>



 **Private cloud deployment**.

 

The other response options are incorrect because:

- Cloud-based applications are fully deployed in the cloud and do not have any parts that run on premises.
- A hybrid deployment connects infrastructure and applications between cloud-based resources and existing resources that are not in the cloud, such as on-premises resources. However, a hybrid deployment is not equivalent to an on-premises deployment because it involves resources that are located in the cloud.
- The AWS Cloud offers three cloud deployment models: cloud, hybrid, and on-premises. This response option is incorrect because the AWS Cloud is not equivalent to only an on-premises deployment.





<u>How does the scale of cloud computing help you to save costs?</u>

The correct response option is **The aggregated cloud usage from a large number of customers results in lower pay-as-you-go prices**.

 

This answer describes how customers can benefit from massive economies of scale in cloud computing.

 

The other response options are incorrect because:

- Not having to invest in technology resources before using them relates to *Trade upfront expense for variable expense*.
- Accessing services on-demand to prevent excess or limited capacity relates to *Stop guessing capacity*.
- Quickly deploying applications to customers and providing them with low latency relates to *Go global in minutes*.