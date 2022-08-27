2/18/22

# Module 3  - AWS Global Infrastructure and Reliability

## **Learning objectives**

In this module, you will learn how to:

- Summarize the **benefits of the AWS Global Infrastructure**.
- Describe the basic concept of **Availability Zones**.
- Describe the **benefits of Amazon CloudFront** and **edge locations**.
- Compare **different methods for provisioning AWS services**.
- 

==High availability and fault tolerance==



Historically, business had to run their own application in their own data centers. 

Hope not a good business plan

AWS builds **regions** - multiple data centers

- high speed fiber network

- **regional data sovereignty is critical design of AWS regions** - any data stored in a region will not leave that region with data being subject to the local laws and statutes in where the region lives

- you get to choose a region :

  1. important to take into account **compliance**

  2. **Proximity** - how close you are to your customer base
     - **latency** - the time it takes for data to be sent and received
       - quantum networking is lightyears away!
  3. **Feature availability** - AWS releases 1000s of new services which takes time to build hardware 
  4. **Pricing** - each region has a different
     - in Brazil expensive compared to other location



## **Selecting a Region**

When determining the right Region for your services, data, and applications, consider the following four business factors. 

To learn more, select the **+** symbol next to each category.

Compliance with data governance and legal requirements

–

Depending on your company and location, you might need to run your data out of specific areas. For example, if <u>your company requires all of its data to reside within the boundaries of the UK, you would choose the London Region</u>. 



Not all companies have location-specific data regulations, so you might need to focus more on the other three factors.

Proximity to your customers

–

Selecting a Region that is close to your customers will help you to get content to them faster. For example, your company is based in Washington, DC, and many of your customers live in Singapore. You might <u>consider running your infrastructure in the Northern Virginia Region to be close to company headquarter</u>s, and <u>run your applications from the Singapore Region</u>.

Available services within a Region

–

Sometimes, the closest Region might not have all the features that you want to offer to customers. AWS is frequently innovating by creating new services and expanding on features within existing services. However, <u>making new services available around the world sometimes requires AWS to build out physical hardware one Region at a time.</u> 



Suppose that your developers want to build an application that uses ==Amazon Braket (AWS quantum computing platform)==. As of this course, Amazon Braket is not yet available in every AWS Region around the world, so your developers would have to run it in one of the Regions that already offers it.

Pricing

–

Suppose that you are considering running applications in both the United States and Brazil. The way Brazil’s tax structure is set up, it might cost 50% more to run the same workload out of the São Paulo Region compared to the Oregon Region. You will learn in more detail that several factors determine pricing, but for now know that the cost of services can vary from Region to Region.



----

### Availability Zone

**availability zone** - a single or group of data centers with redundant power, networking and connectivity

- <u>When you launch an Amazon EC2 instance, it launches a virtual machine on a physical hardware that is installed in an Availability Zone.</u>
  - If you only run one EC2 instance, it only runs in one building, or one Availability Zone

Each region has multiple availability zones

==run across at least 2 Availability Zones in a region==

**Elastic Load Balancing** - regional construct that runs across all AZs, communicating with the EC2 instances that are unning in a specific Availability Zone

![image-20220218153116554](../assets/image-20220218153116554.png)

An <u>**Availability Zone** is a single data center or a group of data centers within a Region</u>. Availability Zones are located tens of miles apart from each other. This is close enough to have <u>low latency (the time between when content requested and received)</u> between Availability Zones. However, if a disaster occurs in one part of the Region, they are distant enough to reduce the chance that multiple Availability Zones are affected.

![image-20220218154139737](../assets/image-20220218154139737.png)

![image-20220218154230035](../assets/image-20220218154230035.png)

![image-20220218154248694](../assets/image-20220218154248694.png)

### Summary

Planning for failure and deploying applications across multiple Availability Zones is an important part of building a resilient and highly available architecture.

The correct response option is **A single data center or group of data centers within a Region**.

 

The other response options are incorrect because:

- A Region is a geographical area that contains AWS resources.
- An ==**edge location** is a data center that an AWS service uses to perform service-specific operations==. Edge locations are examined in the next section of this module.
- <u>**AWS Outposts** is a service that you can use to run AWS infrastructure, services, and tools in your own on-premises data center in a hybrid approach</u>. AWS Outposts is explored later in this module.

**Learn more:**

- [AWS global infrastructure](https://aws.amazon.com/about-aws/global-infrastructure)
- [Regions and Availability Zones](https://aws.amazon.com/about-aws/global-infrastructure/regions_az)

## Edge Locations

caching a local copy for locations that accesses a region that is far away

==CDN - Amazon Cloudfront==

- delivers data with low latency and high transfer speed
- uses edge locations to accelerate communication

==An **edge location** is a site that Amazon CloudFront uses to store cached copies of your content closer to your customers for faster delivery==.

- seperate from regions
- you can push content from inside a region to a collection of Edge locations around the world in order accelerate communication and content delivery.
- runs more than Cloudfront, runs Amazon Route 53, helping customer direct to right locations
- **AWS Outposts** - installs fully operational mini region inside your own data center

**Regions** - geographically isolated areas

- contains AZs

**Edge locations** run Amazon Cloudfront

![image-20220218155110812](../assets/image-20220218155110812.png)

### How to provision AWS resources

use APIs to interact with AWS services

![image-20220218155228923](../assets/image-20220218155228923.png)

### AWS Management Console 



The <u>**AWS Management Console** is a web-based interface for accessing and managing AWS services.</u> You can quickly access recently used services and search for other services by name, keyword, or acronym. The console <u>includes wizards and automated workflows</u> that can simplify the process of completing tasks.

You can also use the AWS Console mobile application to perform tasks such as <u>monitoring resources, viewing alarms, and accessing billing information</u>. Multiple identities can stay logged into the AWS Console mobile app at the same time.



AWS Management Console - browser based

![image-20220218155305194](../assets/image-20220218155305194.png)

### AWS Command Line Interface (AWS CLI)

To save time when making API requests, you can use the **AWS Command Line Interface (AWS CLI)**. AWS CLI enables you to <u>control multiple AWS services directly from the command line within one tool</u>. AWS CLI is available for users on Windows, macOS, and Linux. 



By using AWS CLI, you can <u>automate the actions that your services and applications perform through scripts</u>. For example, you can use commands to <u>launch</u> an Amazon EC2 instance, <u>connect</u> an Amazon EC2 instance to a specific Auto Scaling group, and more.



In a production environment, you won't want to use this click and point style

- manual provisioning - opening up to errors
- Answer - use tools that allow you to script or program API calls
- AWS  CLI - make API calls using the terminal on your machine

![image-20220218155438162](../assets/image-20220218155438162.png)

- less susceptible to human error
- automation important to success

### AWS SDKs

Another option for accessing and managing AWS services is the **software development kits (SDKs)**. SDKs make it easier for you to use AWS services through an API designed for your programming language or platform. SDKs <u>enable you to use AWS services with your existing applications</u> or <u>create entirely new applications that will run on AWS</u>.



To help you get started with using SDKs, AWS provides documentation and sample code for each supported programming language. Supported programming languages include C++, Java, .NET, and more.

<u>AWS SDKs - interact with AWS resources through various programming languages</u>

- makes it easy for devs to create programs that use AWS without using the low-level APIs, as well as avoiding that manual resource creation



![image-20220218160027612](../assets/image-20220218160027612.png)

Other ways:

#### Elastic Beanstalk

**Elastic Beanstalk** - provision Amazon EC2 based environments - takes code and configs and builds out environment for you

- allows you to save configs
- convenience of not having to provision and manage all these pieces seperately

![image-20220218160144907](../assets/image-20220218160144907.png)

![image-20220218160213580](../assets/image-20220218160213580.png)

![image-20220218160302057](../assets/image-20220218160302057.png)

#### AWS CloudFormation

<u>AWS CloudFormation - service to create automated and repeatable deployments</u> 

![image-20220218160342806](../assets/image-20220218160342806.png)

- Infrastructure-as-code tool that allows you to define a <u>wide variety of AWS resources</u> in a declarative way <u>using JSON or YAML</u> text-based documents called <u>CloudFormation templates</u>.
  - declarative
  - allows you to define without worrying about details

![image-20220218163134907](../assets/image-20220218163134907.png)

![image-20220218163210848](../assets/image-20220218163210848.png)

- define resources in an AWS CloudFormation template
- CloudFormation would parse template and begin provisioning resources you defined in parallel



![image-20220218163325968](../assets/image-20220218163325968.png)

![image-20220218163342149](../assets/image-20220218163342149.png)

- manages API calls for you
- multiple accounts
  - and it will create identical env across them
- automated process

## **AWS Elastic Beanstalk**

With <u>**AWS Elastic Beanstalk**, you provide code and configuration settings</u>, and Elastic Beanstalk deploys the resources necessary to perform the following tasks:

- Adjust capacity
- Load balancing
- Automatic scaling
- Application health monitoring

## **AWS CloudFormation**

With **AWS CloudFormation**, you can treat your infrastructure as code. This means that y<u>ou can build an environment by writing lines of code</u> instead of using the AWS Management Console to individually provision resources.

AWS CloudFormation <u>provisions your resources in a safe, repeatable manner</u>, enabling you to frequently build your infrastructure and applications without having to perform manual actions. It <u>determines the right operations to perform when managing your stack and rolls back changes automatically if it detects errors.</u>

In Module 3, you learned about the following concepts:

- AWS Regions and Availability Zones
- Edge locations and Amazon CloudFront
- The AWS Management Console, AWS CLI, and SDKs
- AWS Elastic Beanstalk
- AWS CloudFormation


–

Awesome stuff, I mean, we covered a lot of ground in here. And I don't mean that just because we talked about AWS global infrastructure. 



But seriously, we covered how logical clusters of data centers make up Availability Zones, Availability Zones in turn make up Regions, and those are spread globally. You then choose what Regions and Availability Zones you want to operate out of and as a best practice, you should always deploy infrastructure across at least two Availability Zones. And some AWS services like Elastic Load Balancing, Amazon SQS, and Amazon SNS already do this for you. 



We also talked about Edge locations and how you can deploy content there to speed up delivery to your customers. We even touched upon edge devices like AWS Outposts which allow you to run AWS infrastructure right in your own data center. 



Another thing we discussed was how to provision AWS resources through various options, such as the AWS Management Console, the SDK, CLI, AWS Elastic Beanstalk, and AWS CloudFormation, where you learned how you can set up your infrastructure as code. 



I hope you learned how globally available AWS is and how easy it is to get started with provisioning resources.

## Additional resources

Review these resources to learn more about the concepts that were explored in Module 3.

- [Global Infrastructure](https://aws.amazon.com/about-aws/global-infrastructure/)
- [Interactive map of the AWS Global Infrastructure](https://www.infrastructure.aws/)
- [Regions and Availability Zones](https://aws.amazon.com/about-aws/global-infrastructure/regions_az)
- [AWS Networking and Content Delivery Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/)
- [Tools to Build on AWS](https://aws.amazon.com/tools/)
- [AWS Customer Stories: Content Delivery](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc|product%23api-gateway|product%23cloudfront|product%23route53|product%23directconnect|product%23elb&awsf.customer-references-category=category%23content-delivery)

Amazon CloudFront is a content delivery service. It uses a network of edge locations to cache content and deliver content to customers all over the world. When content is cached, it is stored locally as a copy. This content might be video files, photos, webpages, and so on.

 The other response options are incorrect because:

- AWS Outposts is a service that enables you to run infrastructure in a hybrid cloud approach.
- AWS Fargate is a serverless compute engine for containers.
- Amazon Simple Queue Service (Amazon SQS) is a service that enables you to send, store, and receive messages between software components through a queue.

**AWS Outposts - Extend AWS infrastructure and services to your on-premises data center**.

 

The other response options are incorrect because:

- The AWS Command Line Interface (AWS CLI) is used to automate actions for AWS services and applications through scripts.

- The AWS Management Console includes wizards and workflows that you can use to complete tasks in AWS services.

- Software development kits (SDKs) enable you to develop AWS applications in supported programming languages.

  