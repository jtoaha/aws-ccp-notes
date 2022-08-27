2/12/22

# Module 2: Amazon EC2



## **Learning objectives**

In this module, you will learn how to:

- Describe the benefits of Amazon EC2 at a basic level.
- Identify the different Amazon EC2 instance types.
- Differentiate between the various billing options for Amazon EC2.
- Summarize the benefits of Amazon EC2 Auto Scaling.
- Summarize the benefits of Elastic Load Balancing.
- Give an example of the uses for Elastic Load Balancing.
- Summarize the differences between Amazon Simple Notification Service (Amazon SNS) and Amazon Simple Queue Service (Amazon SQS).
- Summarize additional AWS compute options.



![image-20220213213949665](../assets/image-20220213213949665.png)

When you own your own fleet

- how many, what type, wait for it to be delivered and installed, make sure it's secure, only then you can host

![image-20220214110438807](../assets/image-20220214110438807.png)

- AWS already has a massive amount of compute capacity
  - Request EC2, and they will boot up, and you can stop or start any time
- EC2 runs on top of physical host machines managed by AWS using **virtualization technology** - sharing a machine with multiping instances (aka virtual machines)
  - This idea of sharing underlying hardware is called ==multitenancy==. 
  - Secure, as EC2 doesn't know other EC2 instances on that machine
- Amazon EC2 configurations
- <u>Resizable</u> - can be give more memory and space - ==Vertical scaling==
- You control of <u>networking aspect of EC2</u> - if they are publicly or private accessible
- ==AWS is a Compute-as-a-Service model==



==[
Amazon Elastic Compute Cloud (Amazon EC2)](https://aws.amazon.com/ec2/) provides secure, resizable compute capacity in the cloud as Amazon EC2 instances.==

Imagine you are responsible for the architecture of your company's resources and need to support new websites. With traditional on-premises resources, you have to do the following:

- Spend money upfront to purchase hardware.
- Wait for the servers to be delivered to you.
- Install the servers in your physical data center.
- Make all the necessary configurations.

By comparison, with an Amazon EC2 instance you can use a virtual server to run applications in the AWS Cloud.

- You can provision and launch an Amazon EC2 instance within minutes.
- You can stop using it when you have finished running a workload.
- You pay only for the compute time you use when an instance is running, not when it is stopped or terminated.
- You can save costs by paying only for server capacity that you need or want.

### How Amazon EC2 works

**1. Launch**

- Configure, OS, app server, instance type (hardware configuration)
- specify security settings to control the network traffic

**2. Connect**

**3. Use**

## Amazon EC2 instance types

[Amazon EC2 instance types](https://aws.amazon.com/ec2/instance-types/) are optimized for different tasks. When selecting an instance type, consider the specific needs of your workloads and applications. This might include r<u>equirements for compute, memory, or storage capabilities</u>.



==The **different instance families in EC2** are general purpose, compute optimized, memory optimized, accelerated computing, and storage optimized==

- **General purpose instances** provide a <u>good balance of compute, memory, and networking resources</u>, and can be used for a variety of diverse workloads like <u>web service or code repositories</u>. 
  - application servers
  - gaming servers
  - backend servers for enterprise applications
  - small and medium databases

- **Compute optimized instances** are ideal are ideal for compute-bound applications that benefit from high-performance processor. Can be used for <u>compute-intensive tasks</u> like <u>gaming servers,</u> <u>high performance computing</u> or HPC, and even <u>scientific modeling</u>. 
  - the difference is compute optimized applications are ideal for: 
    - high-performance web servers
    - compute-intensive applications servers
    - dedicated gaming servers. Y
    - You can also use compute optimized instances for batch processing workloads that require processing many transactions in a single group.



- Similarly, **memory optimized instances** are <u>good for memory-intensive task</u>s. are designed to deliver fast performance for workloads that process large datasets in memory. 

  - In computing, memory is a temporary storage area. It holds all the data and instructions that a central processing unit (CPU) needs to be able to complete actions. Before a computer program or application is able to run, it is loaded from storage into memory. This <u>preloading process gives the CPU direct access to the computer program</u>.
  - Example usecase: Suppose that you have a <u>workload that requires large amounts of data to be preloaded</u> before running an application. This scenario might be a <u>high-performance database</u> or a <u>workload that involves performing real-time processing</u> of a large amount of unstructured data.

  

- **Accelerated computing**  use <u>hardware accelerators, or **coprocessors**, to perform some functions more efficiently</u> than is possible in software running on CPUs.

  - are good for <u>floating point number calculations</u>, <u>graphics processing</u>, or <u>data pattern matching</u>, as they use hardware accelerators. 

- And finally, **storage optimized instances** are designed for <u>workloads that require high, sequential read and write access to large datasets on local storage</u>
  - Workloads that require high performance for locally stored data. 
  -  Workloads suitable for storage optimized instances include:
    -  <u>distributed file systems</u>,
    -  <u>data warehousing applications</u>, and 
    - <u>high-frequency online transaction processing</u> (OLTP) systems
  - In computing, the term input/output operations per second **(IOPS)** is a metric that measures the performance of a storage device. It indicates how many different input or output operations a device can perform in one second. Storage optimized instances are <u>designed to deliver tens of thousands of low-latency, random IOPS to applications</u>. 

![image-20220214114327426](../assets/image-20220214114327426.png)

## **Amazon EC2 pricing**

With Amazon EC2, you pay only for the compute time that you use. Amazon EC2 offers a variety of pricing options for different use cases. For example, if your use case can withstand interruptions, you can save with Spot Instances. You can also save by committing early and locking in a minimum level of use with Reserved Instances.

To learn more, select the **+** symbol next to each category.

On-Demand

–

**On-Demand Instances** are ideal for s<u>hort-term, irregular workloads that cannot be interrupted</u>. No upfront costs or minimum contracts apply. The instances run continuously until you stop them, and you pay for only the compute time you use.

Sample use cases for On-Demand Instances include developing and testing applications and running applications that have <u>unpredictable usage patterns</u>. On-Demand Instances are <u>not recommended for workloads that last a year or longer</u> because these workloads can experience greater cost savings using Reserved Instances.

Amazon EC2 Savings Plans

–

AWS offers Savings Plans for several compute services, including Amazon EC2. **Amazon EC2 Savings Plans** enable you to reduce your compute costs by committing to a <u>consistent amount of compute usage for a 1-year or 3-year term</u>. This term commitment results in <u>savings of up to 66%</u> over On-Demand costs.



Any usage up to the commitment is charged at the discounted plan rate (for example, $10 an hour). Any usage beyond the commitment is charged at regular On-Demand rates.



Later in this course, you will review AWS Cost Explorer, a tool that enables you to visualize, understand, and manage your AWS costs and usage over time. <u>If you are considering your options for Savings Plans, AWS Cost Explorer can analyze your Amazon EC2 usage over the past 7, 30, or 60 days</u>. AWS Cost Explorer also provides customized recommendations for Savings Plans. These recommendations estimate how much you could save on your monthly Amazon EC2 costs, based on previous Amazon EC2 usage and the hourly commitment amount in a 1-year or 3-year plan.

Reserved Instances

–

**Reserved Instances** are a <u>billing discount applied to the use of On-Demand Instances in your account</u>. You can purchase Standard Reserved and Convertible Reserved Instances for a 1-year or 3-year term, and Scheduled Reserved Instances for a 1-year term. <u>You realize greater cost savings with the 3-year option</u>.



<u>At the end of a Reserved Instance term</u>, you can continue using the Amazon EC2 instance without interruption. However, <u>you are charged On-Demand rates</u> until you do one of the following:

- Terminate the instance.
- Purchase a new Reserved Instance that matches the instance attributes (instance type, Region, tenancy, and platform).

Spot Instances

–

**Spot Instances** are ideal for workloads with <u>flexible start and end times</u>, or that can withstand interruptions. Spot Instances use <u>unused Amazon EC2 computing capacity</u> and offer you cost savings at up to <u>90% off</u> of On-Demand prices.

Suppose that you have a background processing job that can start and stop as needed (such as the data processing job for a customer survey). You want to start and stop the processing job without affecting the overall operations of your business. If you make a Spot request and Amazon EC2 capacity is available, your Spot Instance launches. However, if you make a Spot request and Amazon EC2 capacity is unavailable, the request is not successful until capacity becomes available. The unavailable capacity might delay the launch of your background processing job.

After you have launched a Spot Instance, if capacity is no longer available or demand for Spot Instances increases, your instance may be interrupted. This might not pose any issues for your background processing job. However, in the earlier example of developing and testing applications, you would most likely want to avoid unexpected interruptions. Therefore, choose a different EC2 instance type that is ideal for those tasks.

Dedicated Hosts

–

**Dedicated Hosts** are physical servers with Amazon EC2 instance capacity that is fully dedicated to your use. 



You can use your existing per-socket, per-core, or per-VM software licenses to help maintain license compliance. You can purchase <u>On-Demand Dedicated Hosts</u> and <u>Dedicated Hosts Reservations</u>. Of all the Amazon EC2 options that were covered, <u>Dedicated Hosts are the most expensive.</u>


## Scaling Amazon EC2

Scalability and Elasticity - capacity can shrink or grow 

==Everything fails all the time, so plan for failure and nothing fails - Werner Vogel==

**Scalability** involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling out or in. 

-  **Amazon EC2 Auto Scaling** : automates scaling process


## Amazon EC2 Auto Scaling

Within Amazon EC2 Auto Scaling, you can use two approaches: dynamic scaling and predictive scaling.

- *Dynamic scaling* responds to changing demand. 
- *Predictive scaling* automatically schedules the right number of Amazon EC2 instances based on predicted demand.

![image-20220214120322219](../assets/image-20220214120322219.png)

- desired capacity defaults to minimum capacity if not set

The third configuration that you can set in an Auto Scaling group is the **maximum capacity**. For example, you might configure the Auto Scaling group to scale out in response to increased demand, but only to a maximum of four Amazon EC2 instances.

Because Amazon EC2 Auto Scaling uses Amazon EC2 instances, you pay for only the instances you use, when you use them. You now have a cost-effective architecture that provides the best customer experience while reducing expenses.

## Directing traffic with Elastic Load Balancing

load balancer - takes in instance and directs

Elastic Load Balancing (regional construct) - bc it runs regi

![image-20220214120900226](../assets/image-20220214120900226.png)

![image-20220214121052187](../assets/image-20220214121052187.png)

- each front end instance is area of backend instance in this case, becomes complicated with hundreds

![image-20220214121138645](../assets/image-20220214121138645.png)

- and if a new instance comes online, it would need to tell every front end instance, with a load balancer this does not matter: 

![image-20220214121208175](../assets/image-20220214121208175.png)

- Each front end can access a single ELB instance 
- if the backend scales, it can tell the ELB, and it gets to work, front end doesnt' know and doesn't care!

## **Elastic Load Balancing**

==**Elastic Load Balancing** is the AWS service that automatically distributes incoming application traffic across multiple resources, such as Amazon EC2 instances.==



**A load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group**. This means that as you add or remove <u>Amazon EC2 instances</u> in response to the amount of incoming traffic, <u>these requests route to the load balancer first</u>. Then, the requests spread across multiple resources that will handle them. For example, if you have multiple Amazon EC2 instances, **Elastic Load Balancing distributes the workload across the multiple instances so that no single instance has to carry the bulk of it.** 

Although <u>Elastic Load Balancing and Amazon EC2 Auto Scaling are separate services, they work togethe</u>r to help ensure that applications running in Amazon EC2 can <u>provide high performance and availability</u>. 

Low Demand Period vs High Demand Period

## Messaging and queuing

**Tightly-coupled architecture** - hallmark trait, if single component fails, it causes problem for other components or entire system

**Loosely coupled architecture:** Single failure won't cause cascading failures

- more reliable
- ![image-20220214122852292](../assets/image-20220214122852292.png)
  - Amazon Simple Queue Service **(Amazon SQS)**
    - where data is placed before they are processed
    - send, store, receive messages at any volume between components
    - Payload
  - Amazon Simple Notification Service (**Amazon SNS**)
    - it can also send out notifications to end users using a <u>pub-subscribe service</u>
      - Amazon SNS topic:  a channel for messages to be delivered
        - configure subscribers (can be end points, https, etc) and publishes messages to subscribers. 
    - ==In Amazon SNS, subscribers can be <u>web servers</u>, <u>email addresses</u>, <u>AWS Lambda functions</u>, or several other options==

### Monolithic applications and microservices

Suppose that you have an application with tightly coupled components. These components might include databases, servers, the user interface, business logic, and so on. This type of architecture can be considered a **monolithic application**. 

To help maintain application availability when a single component fails, you can design your application through a **microservices** approach.

- In a microservices approach, <u>application components are loosely coupled</u>. In this case, if <u>a single component fails</u>, the <u>other components continue to work</u> because they are communicating with each other. The loose coupling prevents the entire application from failing. 

When <u>designing applications on AWS</u>, you <u>can take a microservices approach</u> with se<u>rvices and components that fulfill different functions</u>. Two services facilitate application integration: Amazon Simple Notification Service (Amazon SNS) and Amazon Simple Queue Service (Amazon SQS).

### **Amazon Simple Notification Service (Amazon SNS)**

**Amazon Simple Notification Service (Amazon SNS)** is a publish/subscribe service. Using Amazon SNS topics, a publisher publishes messages to subscribers. This is similar to the coffee shop; the cashier provides coffee orders to the barista who makes the drinks.

In Amazon SNS, subscribers can be web servers, email addresses, AWS Lambda functions, or several other options. 

### **Amazon Simple Queue Service (Amazon SQS)**

**Amazon Simple Queue Service (Amazon SQS)** is a message queuing service. 

Using Amazon SQS, you can send, store, and receive messages between software components, without losing messages or requiring other services to be available. <u>In Amazon SQS, an application sends messages into a queue</u>. A user or service retrieves a message from the queue, processes it, and then deletes it from the queue.

![image-20220214124143890](../assets/image-20220214124143890.png)

![image-20220214124243422](../assets/image-20220214124243422.png)

For decoupled applications and microservices, Amazon SQS enables you to send, store, and retrieve messages between components. 

This decoupled approach enables the separate components to work more efficiently and independently. 

## Additional compute services

EC2 - set up fleet of instances over time

When you're using EC2, you are responsible for patching your instances when new software packages come out, setting up the scaling of those instances as well as ensuring that you've architected your solutions to be hosted in a highly available manner



 AWS offers multiple serverless compute options.

- Serverless means that you cannot actually see or access the underlying infrastructure or instances that are hosting your application. Instead, all the management of the underlying environment from a provisioning, scaling, high availability, and maintenance perspective are taken care of for you

- ==**AWS Lambda** - one serverless compute option==
  - Lambda's a service that allows you to <u>upload your code into what's called a Lambda function</u>. <u>Configure a trigger</u> and from there, the service waits for the trigger. When the trigger is detected, the <u>code is automatically run in a managed environment</u>, an environment you do not need to worry too much about because it is **automatically scalable, highly available and all of the maintenance in the environment itself is done by AWS**
  - Run time < 15 minutes
    - more suited for backend handling requests
    - backend expense report processing service where each invocation takes less than 15 min to complete

If you weren't quite ready for serverless yet or <u>you need access to the underlying environment</u>, but still want <u>efficiency and portability</u>, you should look at AWS container services like **Amazon Elastic Container Service,** otherwise known as ECS. Or **Amazon Elastic Kubernetes Service**, otherwise known as EKS. 

- Container orchestration tools - to help manage 
- Docker'
- Container: package for your code
  - these containers run on top of EC2 instances
- Cluster of containers you need to manage
- ECS - at scale
- EKS - different toolings and different features

AWS fargate - serverless option for ECS and EKS

![image-20220214125839444](../assets/image-20220214125839444.png)

![image-20220214125857799](../assets/image-20220214125857799.png)



![image-20220214125914828](../assets/image-20220214125914828.png)

## **Serverless computing**

Earlier in this module, you learned about Amazon EC2, a service that lets you run virtual servers in the cloud. If you have applications that you want to run in Amazon EC2, you must do the following:

1. Provision instances (virtual servers)

2. Upload your code
3. Continue to manage the instances while your application is running.

![Illustration comparing computing with virtual servers (thinking about servers and code) and serverless computing (thinking only about code)](../assets/FOkwI-hxTA07WaKF_AKDPOn1ZYEHZsxk4.png)

The term “serverless” means that your code runs on servers, but you do not need to provision or manage these servers. With serverless computing, you can focus more on innovating new products and features instead of maintaining servers.

Another benefit of serverless computing is the flexibility to scale serverless applications automatically. Serverless computing can adjust the applications' capacity by modifying the units of consumptions, such as throughput and memory. 

An AWS service for serverless computing is **AWS Lambda**.

## **AWS Lambda**

==[**AWS Lambda**](https://aws.amazon.com/lambda) is a service that lets you run code without needing to provision or manage servers.==

While using AWS Lambda, you <u>pay only for the compute time that you consume</u>. Charges apply only when your code is running. You can also <u>run code for virtually any type of application or backend service, all with zero administration</u>. 

For example, <u>a simple Lambda function might involve automatically resizing uploaded images to the AWS Cloud</u>. In this case, the function triggers when uploading a new image. 

![image-20220214130259171](../assets/image-20220214130259171.png)

1. You upload your code to Lambda. 
2. You set your code to trigger from an event source, such as AWS services, mobile applications, or HTTP endpoints
3. Lambda runs your code only when triggered.
4. You pay only for the compute time that you use. In the previous example of resizing images, you would pay only for the compute time that you use when uploading new images. Uploading the images triggers Lambda to run code for the image resizing function.

==In AWS, you can also build and run **containerized** application==

## **Containers**

**Containers** provide you with a standard way to <u>package your application's code and dependencies into a single object</u>. You can also use containers for <u>processes</u> and <u>workflows</u> in which there are <u>essential requirements for security, reliability, and scalability</u>.

==Question: In virtualization and creating different virtual machine instances, are thse also considered containers==

- maybe containers are more specific

#### One host with multiple containers

Suppose that a company’s application developer has an environment on their computer that is different from the environment on the computers used by the IT operations staff. The developer wants to ensure that the application’s environment remains consistent regardless of deployment, so they use a containerized approach. This helps to <u>reduce time spent debugging applications and diagnosing differences in computing environments</u>.

#### Tens of hosts with hundreds of containers

When running containerized applications, <u>it’s important to consider scalability</u>. Suppose that instead of a single host with multiple containers, you have to manage tens of hosts with hundreds of containers. Alternatively, you have to manage possibly hundreds of hosts with thousands of containers. At a large scale, imagine <u>how much time it might take for you to monitor memory usage, security, logging, and so on</u>.

<u>Container orchestration services help you to deploy, manage, and scale your containerized applications</u>. Next, you will learn about two services that provide container orchestration: Amazon Elastic Container Service and Amazon Elastic Kubernetes Service.

## **Amazon Elastic Container Service (Amazon ECS)**

==[**Amazon Elastic Container Service (Amazon ECS)**](https://aws.amazon.com/ecs/) is a <u>highly scalable, high-performance container management system</u> that enables you to run and scale containerized applications on AWS.==

Amazon ECS <u>supports Docker containers</u>. ==[Docker](https://www.docker.com/) is a software platform that enables you to build, test, and deploy applications quickly==. AWS supports the use of <u>open-source Docker Community Edition</u> and <u>subscription-based Docker Enterprise Edition</u>. With Amazon ECS, you can use API calls to launch and stop Docker-enabled applications.

## **Amazon Elastic Kubernetes Service (Amazon EKS)**

==[**Amazon Elastic Kubernetes Service (Amazon EKS)**](https://aws.amazon.com/eks/) is a fully managed service that you can use to <u>run Kubernetes</u> on AWS.==

[Kubernetes](https://kubernetes.io/) is <u>open-source software that enables you to deploy and manage containerized applications at scale.</u> A large community of volunteers maintains Kubernetes, and AWS actively works together with the Kubernetes community. As new features and functionalities release for Kubernetes applications, you can easily apply these updates to your applications managed by Amazon EKS.

## **AWS Fargate**

==[**AWS Fargate**](https://aws.amazon.com/fargate/) is a **serverless compute engine for containers**. It works with both Amazon ECS and Amazon EKS.==

When using AWS Fargate, you do not need to provision or manage servers. <u>AWS Fargate manages your server infrastructure for you</u>. You can focus more on innovating and developing your applications, and you pay only for the resources that are required to run your containers.



### Summary



In Module 2, you learned about the following concepts:

- Amazon EC2 instance types and pricing options
- Amazon EC2 Auto Scaling
- Elastic Load Balancing
- AWS services for messaging, containers, and serverless computing



![image-20220214131310275](../assets/image-20220214131310275.png)

- Compute, networking, analytics, can be made available for you on demand

EC2 - to spin services

![image-20220214131358066](../assets/image-20220214131358066.png)

- can be scaled vertically or horizontally

![image-20220214131439324](../assets/image-20220214131439324.png)

Messsaging Services: 



virtual services, container orchestration tools

AWS Lamda -



Hey everyone, I hope you've been enjoying the course so far. We're going to do check-ins like this one after each major topic to review what you've learned. 



First things first, what is cloud computing and what does AWS offer? We define cloud computing as the on-demand delivery of IT resources over the internet with pay-as-you-go pricing. This means that you can make requests for IT resources like compute, networking, storage, analytics, or other types of resources, and then they're made available for you on demand. You don't pay for the resource upfront. Instead, you just provision and pay at the end of the month. 



AWS offers services and many categories that you use together to create your solutions. We've only covered a few services so far, you learned about Amazon EC2. With EC2, you can dynamically spin up and spin down virtual servers called EC2 instances. When you launch an EC2 instance, you choose the instance family. The instance family determines the hardware the instance runs on. 



And you can have instances that are built for your specific purpose. The categories are general purpose, compute optimized, memory optimized, accelerated computing, and storage optimized. 



You can scale your EC2 instances either vertically by resizing the instance, or horizontally by launching new instances and adding them to the pool. You can set up automated horizontal scaling, using Amazon EC2 Auto Scaling. 



Once you've scaled your EC2 instances out horizontally, you need something to distribute the incoming traffic across those instances. This is where the Elastic Load Balancer comes into play. 

EC2 instances have different pricing models. There is On-Demand, which is the most flexible and has no contract, spot pricing, which allows you to utilize unused capacity at a discounted rate, Savings Plans or Reserved Instances, which allow you to enter into a contract with AWS to get a discounted rate when you commit to a certain level of usage, and Savings Plans which apply to AWS Lambda, and AWS Fargate, as well as EC2 instances. 



We also covered messaging services. There is Amazon Simple Queue Service or SQS. This service allows you to decouple system components. Messages remain in the queue until they are either consumed or deleted. Amazon Simple Notification Service or SNS, is used for sending messages like emails, text messages, push notifications, or even HTTP requests. Once a message is published, it is sent to all of these subscribers. 



You also learned that AWS has different types of compute services beyond just virtual servers like EC2. There are container services like Amazon Elastic Container Service, or ECS. And there's Amazon Elastic Kubernetes Service, or EKS. Both of which are container orchestration tools. You can use these tools with EC2 instances, but if you don't want to manage that, you don't need to. 



You can use AWS Fargate, which allows you to run your containers on top of a serverless compute platform. Then there is AWS Lambda, which allows you to just upload your code, and configure it to run based on triggers. And you only get charged for when the code is actually running. No containers, no virtual machines. Just code and configuration. 

Hopefully that sums it up. Catch you in the next one.

## **Additional resources**

To learn more about the concepts that were explored in Module 2, review these resources.

- [Compute on AWS](https://aws.amazon.com/products/compute)
- [AWS Compute Blog](https://aws.amazon.com/blogs/compute/)
- [AWS Compute Services](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/compute-services.html)
- [Hands-On Tutorials: Compute](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23compute&awsf.getting-started-content-type=content-type%23hands-on)
- [Category Deep Dive: Serverless](https://aws.amazon.com/getting-started/deep-dive-serverless/)
- [AWS Customer Stories: Serverless](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc|product%23api-gateway|product%23cloudfront|product%23route53|product%23directconnect|product%23elb&awsf.customer-references-category=category%23serverless)

## Quiz

You want to use an Amazon EC2 instance for a batch processing workload. What would be the best Amazon EC2 instance type to use? Compute optimized



The other response options are incorrect because:

- General purpose instances provide a balance of compute, memory, and networking resources. This instance family would not be the best choice for the application in this scenario. Compute optimized instances are more well suited for batch processing workloads than general purpose instances.
- Memory optimized instances are more ideal for workloads that process large datasets in memory, such as high-performance databases.
- Storage optimized instances are designed for workloads that require high, sequential read and write access to large datasets on local storage. The question does not specify the size of data that will be processed. Batch processing involves processing data in groups. A compute optimized instance is ideal for this type of workload, which would benefit from a high-performance processor.

---

Reserved Instances require a commitment of either 1 year or 3 years. The 3-year option offers a larger discount.

---

You have a workload that will run for a total of 6 months and can withstand interruptions. What would be the most cost-efficient Amazon EC2 purchasing option? Spot Instance

 

The other response options are incorrect because:

- Reserved Instances require a contract length of either 1 year or 3 years. The workload in this scenario will only be running for 6 months.
- Dedicated Instances run in a virtual private cloud (VPC) on hardware that is dedicated to a single customer. They have a higher cost than the other response options, which run on shared hardware.
- On-Demand Instances fulfill the requirements of running for only 6 months and withstanding interruptions. However, a Spot Instance would be the best choice because it does not require a minimum contract length, is able to withstand interruptions, and costs less than an On-Demand Instance.

----

Which process is an example of Elastic Load Balancing?

Ensuring that no single Amazon EC2 instance has to carry the full workload on its own



Autoscaling: 

- Removing unneeded Amazon EC2 instances when demand is low

  Correctly unselected

  

  Adding a second Amazon EC2 instance during an online store’s popular sale

  Correctly unselected

  

  Automatically adjusting the number of Amazon EC2 instances to meet demand

---

**Amazon Elastic Kubernetes Service (Amazon EKS)**.

 

Amazon EKS is a fully managed Kubernetes service. Kubernetes is open-source software that enables you to deploy and manage containerized applications at scale.

 

The other response options are incorrect because:

- AWS Lambda is a service that lets you run code without provisioning or managing servers.
- Amazon Simple Queue Service (Amazon SQS) is a service that enables you to send, store, and receive messages between software components through a queue.
- Amazon Simple Notification Service (Amazon SNS) is a publish/subscribe service. Using Amazon SNS topics, a publisher publishes messages to subscribers.

You want to deploy and manage containerized applications. Which service should you use?
