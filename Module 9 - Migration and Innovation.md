5/30/22

# Module 9 - Migration and Innovation

## **Learning objectives**

In this module, you will learn how to:

- Understand <u>migration and innovation in the AWS Cloud.</u>
- Summarize the <u>AWS Cloud Adoption Framework (AWS CAF)</u>. 
- Summarize the <u>six key factors of a cloud migration strategy.</u>
- Describe the benefits of AWS data migration solutions, such as <u>AWS Snowcone, AWS Snowball, and AWS Snowmobil</u>e.
- Summarize the broad scope of innovative solutions that AWS offers.

## AWS Cloud Adoption Framework (AWS CAF)

What position you hold in your organization will impact what you need to know to migrate: 

- Developer, cloud architect, business analyst
- harness different perspective
- Cloud Adoption Framework - exists to provide quick and smooth migration to AWS 

![image-20220530220329930](Module%209%20-%20Migration%20and%20Innovation.assets/image-20220530220329930.png)

AWS CAF Perspectives

- Business Capabilities: 
  - Business - business or finance analysit
  - People - hr
  - Governance
- Technical Capabilities:
  - Platform - architect
  - Security
  - Operations

Each perspective is used to uncover gaps in your skills and processes, which are then recorded as inputs, which are then used as the basis for creating what is the <u>AWS Cloud Adoption Framework Action Plan:</u> 

- **AWS CAF Action Plan:** Helps guide your organization for cloud migration 
- can keep you on track, tons of resources to help you get started and the CAF is a great place to look

### ==**Six core perspectives of the Cloud Adoption Framework**==

At the highest level, the [**AWS Cloud Adoption Framework (AWS CAF)**](https://d1.awsstatic.com/whitepapers/aws_cloud_adoption_framework.pdf) organizes guidance into six areas of focus, called **P****erspectives**. Each Perspective addresses distinct responsibilities. The planning process helps the right people across the organization prepare for the changes ahead.

In general, the **Business**, **People**, and **Governance** Perspectives focus on business capabilities, whereas the **Platform**, **Security**, and **Operations** Perspectives focus on technical capabilities.

To learn more, select the **+** symbol next to each category.

Business Perspective

–

The **Business Perspective** ensures that IT aligns with business needs and that IT investments link to key business results.



Use the Business Perspective to create <u>a strong business case for cloud adoption and prioritize cloud adoption initiatives</u>. Ensure that your business strategies and goals align with your IT strategies and goals.



Common roles in the Business Perspective include: 

- Business managers
- Finance managers
- Budget owners
- Strategy stakeholders

**<u>People Perspective</u>**

–

The **People Perspective** supports development of an organization-wide change management strategy for successful cloud adoption.



Use the People Perspective to <u>evaluate organizational structures and roles, new skill and process requirements, and identify gaps.</u> This helps prioritize training, staffing, and organizational changes.



Common roles in the People Perspective include: 

- Human resources
- Staffing
- People managers

<u>**Governance Perspective**</u>

–

The **Governance Perspective** focuses on the skills and processes to align IT strategy with business strategy. This ensures that you maximize the business value and minimize risks.

Use the Governance Perspective to understand how to update the staff skills and processes necessary to ensure business governance in the cloud. Manage and measure cloud investments to evaluate business outcomes.

Common roles in the Governance Perspective include: 

- Chief Information Officer (CIO)
- Program managers
- Enterprise architects
- Business analysts
- Portfolio managers

<u>**Platform Perspective**</u>

–

The **Platform Perspective** includes <u>principles and patterns for implementing new solutions on the cloud, and migrating on-premises workloads to the cloud</u>.



Use a variety of architectural models to understand and communicate the structure of IT systems and their relationships. Describe the architecture of the target state environment in detail.



Common roles in the Platform Perspective include: 

- Chief Technology Officer (CTO)
- IT managers
- Solutions architects

<u>**Security Perspective**</u>

–

The **Security Perspective** ensures that the organization meets security objectives for visibility, auditability, control, and agility. 



Use the AWS CAF to structure the selection and implementation of security controls that meet the organization’s needs.



Common roles in the Security Perspective include: 

- Chief Information Security Officer (CISO)
- IT security managers
- IT security analysts

<u>**Operations Perspective**</u>

–

The **Operations Perspective** helps you to <u>enable, run, use, operate, and recover IT workloads to the level agreed upon with your business stakeholder</u>s.

Define how day-to-day, quarter-to-quarter, and year-to-year business is conducted. Align with and support the operations of the business. The AWS CAF helps these stakeholders define current operating procedures and identify the process changes and training needed to implement successful cloud adoption.

Common roles in the Operations Perspective include: 

- IT operations managers
- IT support managers

---

Which Perspective of the AWS Cloud Adoption Framework helps you design, implement, and optimize your AWS infrastructure based on your business goals and perspectives?

The correct response option is **Platform Perspective**.

The Platform Perspective of the AWS Cloud Adoption Framework also includes principles for implementing new solutions and migrating on-premises workloads to the cloud.

 The other response options are incorrect because:

- The Business Perspective helps you to move from a model that separates business and IT strategies into a business model that integrates IT strategy.
- The Operations Perspective focuses on operating and recovering IT workloads to meet the requirements of your business stakeholders.
- The People Perspective helps Human Resources (HR) employees prepare their teams for cloud adoption by updating organizational processes and staff skills to include cloud-based competencies.

**Learn more:**

- [Whitepaper: An Overview of the AWS Cloud Adoption Framework](https://d1.awsstatic.com/whitepapers/aws_cloud_adoption_framework.pdf)

---

## Migration Strategies

6 options when it comes to enterprise migration. 

Once you have gone through discovery phases, you can decide which is the best fit based on time, cost, priority, etc

1. **Rehosting** - lift and shift 
   - no changes, at least not at first
   - save 30 % of cost just by rehosting
   - easier to optimize application once it lives in the cloud
2. **Replatforming** - lift, tinker and shift
   - Basic lift and shift
   - not touching core code in the process - no new dev process provided here
   - ex. take existing mysql database and you can replatform on RDS mySQL or consider updating to Aurora without code changes
   - 2 of the  6 r's don't actually end up on AWS
3. **<u>Retire</u>** - some parts of enterprise portfolio are no longer needed
   - 10-20 percent includes applications no longer used or already has replacements
   - sometimes you have to turn off lights
4. **<u>Retain</u>** - some applications are about to be deprecated, but you still need them
   - only migrate what makes sense for your business
5. **<u>Repurchase</u>** - common for companies looking to abandon legacy software vendors
   - ex. ending contract with old CRM vendor and moving to new one or ending licensing with out of site database vendor and instead offering cloud native based data offerings
   - remember now dealing with new software package, so total upfront cost goes up, but benefits could go up
6. **<u>Refactoring</u>** - this is driven by business need to add features or improve performance, which might not have been possible on premise
   - Highest intiial cost in terms of planning and human effort, though has long term benefits

### **6 strategies for migration**

When migrating applications to the cloud, six of the most common [migration strategies](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/) that you can implement are:

- Rehosting
- Replatforming
- Refactoring/re-architecting
- Repurchasing
- Retaining
- Retiring

To learn more, select the **+** symbol next to each category.

<u>**Rehosting**</u>

–

<u>**Rehosting** also known as “lift-and-shift” involves moving applications without changes.</u> 

In the scenario of a large legacy migration, in which the company is looking to implement its migration and scale quickly to meet a business case, the majority of applications are rehosted.  

<u>**Replatforming**</u>

–

<u>**Replatforming**, also known as “lift, tinker, and shift,” involves making a few cloud optimizations to realize a tangible benefit. O</u>ptimization is achieved without changing the core architecture of the application.

<u>**Refactoring/re-architecting**</u>

–

<u>**Refactoring** (also known as **re-architecting**) involves reimagining how an application is architected and developed by using cloud-native features.</u> Refactoring is driven by a strong business need to add features, scale, or performance that would otherwise be difficult to achieve in the application’s existing environment.

<u>**Repurchasing**</u>

–

<u>**Repurchasing** involves moving from a traditional license to a software-as-a-service model.</u> 



For example, a business might choose to implement the repurchasing strategy by migrating from a customer relationship management (CRM) system to Salesforce.com.

**<u>Retaining</u>**

–

<u>**Retaining** consists of keeping applications that are critical for the business in the source environment.</u> This might include applications that require major refactoring before they can be migrated, or, work that can be postponed until a later time.

**<u>Retiring</u>**

–

<u>**Retiring** is the process of removing applications that are no longer needed.</u>



---

<u>**Which migration strategy involves moving to a different product?**</u>

The correct response option is **Repurchasing**.

**Repurchasing** involves replacing an existing application with a cloud-based version, such as software found in AWS Marketplace. 

The other response options are incorrect because:

- **Refactoring** involves changing how an application is architected and developed, typically by using cloud-native features.
- **Retiring** involves removing an application that is no longer used or that can be turned off.
- **Replatforming** involves selectively optimizing aspects of an application to achieve benefits in the cloud without changing the core architecture of the application. It is also known as “lift, tinker, and shift.”

**Learn more:**

- [6 Strategies for Migrating Applications to the Cloud](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/)

## AWS Snow Family

Usual route - copy data over which can take days weeks, months

- ==A network with 1 Gbps speed moves 1 PB of data in about 100 days.==
- to address this gap, snow family of devices introduced

**AWS Snowcone** - 8 tb of data and contains edge computing (EC2, IOT)

- Ship it, copy data, ship back
- analytics data, video libraries, image data, tape replacement data

**AWS Snowball Edge** - 2 types: snowball edge  and snowball storage optimization 

- can be clustered for greater computing needs
- can run lambda, ec2 compatible ami, amazon iot greenrust ?
- customers ship to location
- streams from iot devices, industrial signaling

**AWS Snowmobile** - 45 ft rugged shipping container

- houses 100 pb, and ideal for largest migration and even data center shutdowns
- tamper resistant, auto control and evne has a fire suppression and gps tracking, escort security vehicle during transit

All snowfamily devices are designed to be secure and tamper-resistant on-site and while in transit 

- Hardware and software is cryptographically signed and all data store is automatically encrypted using 256 bit encryption keys owned by customers





### **AWS Snow Family members**

The [**AWS Snow Family**](https://aws.amazon.com/snow) is a collection of physical devices that help to physically transport up to exabytes of data into and out of AWS. 

AWS Snow Family is composed of **AWS Snowcone**, **AWS Snowball**, and **AWS Snowmobile**. 

![Illustration of the three AWS Snow Family members: AWS Snowcone, AWS Snowball, and AWS Snowmobile](Module%209%20-%20Migration%20and%20Innovation.assets/qPL6my7HCJPXBNpc_IIcwz3-CkuSyAs0F.jpg)

These devices offer different capacity points, and most include built-in computing capabilities. AWS owns and manages the Snow Family devices and integrates with AWS security, monitoring, storage management, and computing capabilities.  

To learn about each category, select each tab.



==[**AWS Snowcone**](https://aws.amazon.com/snowcone) is a small, rugged, and secure edge computing and data transfer device.==

- It features 2 CPUs, 4 GB of memory, and 8 TB of usable storage.



==[**AWS Snowball**](https://aws.amazon.com/snowball/) offers two types of devices==:

- **Snowball Edge Storage Optimized** 

  devices are well suited for <u>large-scale data migrations and recurring transfer workflows</u>, in addition to local computing with higher capacity needs. 

  - Storage: 80 TB of hard disk drive (HDD) capacity for block volumes and Amazon S3 compatible object storage, and 1 TB of SATA solid state drive (SSD) for block volumes. 
  - Compute: 40 vCPUs, and 80 GiB of memory to support Amazon EC2 sbe1 instances (equivalent to C5).

- **Snowball Edge Compute Optimized** 

  provides powerful computing resources for use cases such as machine learning, full motion video analysis, analytics, and local computing stacks. 

  - Storage: 42-TB usable HDD capacity for Amazon S3 compatible object storage or Amazon EBS compatible block volumes and 7.68 TB of usable NVMe SSD capacity for Amazon EBS compatible block volumes. 
  - Compute: 52 vCPUs, 208 GiB of memory, and an optional NVIDIA Tesla V100 GPU. Devices run Amazon EC2 sbe-c and sbe-g instances, which are equivalent to C5, M5a, G3, and P3 instances.

==[**AWS Snowmobile**](https://aws.amazon.com/snowmobile) is an exabyte-scale data transfer service used to move large amounts of data to AWS.==

- You can transfer up to 100 petabytes of data per Snowmobile, a 45-foot long ruggedized shipping container, pulled by a semi trailer truck.

## Innovation with AWS

VMWare Cloud on AWS

- The same VMware based infrastructure that you use on prem can in many cases, just be lifted up and dropped onto AWS via VMware Cloud on AWS.

When it comes to machine learning and artificial intelligence, AWS has the broadest and deepest set of machine learning and AI services for your business. You can choose from pre-trained AI services for computer vision, language recommendations, and forecasting. **Amazon SageMaker**: Quickly build, train, and deploy machine learning models at scale. 

Or build custom models with support for all the popular open-source frameworks. Our capabilities are built on the most comprehensive cloud platform, <u>optimized for machine learning with high performance compute and no compromises on security and analytics.</u> Tools like Amazon **SageMaker** and Amazon **Augmented AI,** or Amazon **A2I**, provide a machine learning platform that <u>any business can build upon without needing PhD level expertise in-house</u>. Or perhaps, **ready-to-go AI solutions like Amazon Lex, the heart of Alexa.** Helps you build interactive chat bots.

Or what about Amazon **Textract.** Extracting text and data from documents to make them more usable for your enterprise instead of them just being locked away in a repository. 

Do you wanna put machine learning literally into the hands of your developers? Why not try AWS **DeepRacer**? A chance for your developers to experiment with <u>reinforcement learning</u>. One of the newest branches of machine learning algorithms, all while having fun in a racing environment. 

Speaking of communication around the world, have you ever wanted to have your own satellite? Too expensive to launch your own? Why not just use **AWS Ground Station** and only pay for the satellite time you actually need? 

### **Innovate with AWS Services**

When examining how to use AWS services, it is important to focus on the desired outcomes. <u>You are properly equipped to drive innovation in the cloud if you can clearly articulate the following conditions:</u> 

- <u>The current state</u>
- <u>The desired state</u>
- <u>The problems you are trying to solve</u>

Consider some of the paths you might explore in the future as you continue on your cloud journey. 

To learn more, select the **+** symbol next to each category.

<u>**Serverless applications**</u>

–

<u>With AWS, **serverless** refers to applications that don’t require you to provision, maintain, or administer servers</u>. You don’t need to worry about fault tolerance or availability. AWS handles these capabilities for you.



AWS Lambda is an example of a service that you can use to run serverless applications. If you design your architecture to <u>trigger Lambda functions to run your code</u>, you can bypass the need to manage a fleet of servers.



Building your architecture with serverless applications enables your developers to focus on their core product instead of managing and operating servers.

<u>**Artificial intelligence**</u>

–

AWS offers a variety of services powered by **artificial intelligence (AI)**. 



For example, you can perform the following tasks:

- Convert speech to text with Amazon Transcribe.
- Discover patterns in text with Amazon Comprehend.
- Identify potentially fraudulent online activities with Amazon Fraud Detector.
- Build voice and text chatbots with Amazon Lex.

<u>**Machine learning**</u>

–

Traditional **machine learning (ML)** development is complex, expensive, time consuming, and error prone. AWS offers Amazon SageMaker to remove the difficult work from the process and empower you to build, train, and deploy ML models quickly.



You can use ML to analyze data, solve complex problems, and predict outcomes before they happen.

**<u>Which service enables you to quickly build, train, and deploy machine learning models?</u>**

The correct response option is **Amazon SageMaker**.

 

With Amazon SageMaker, you can quickly and easily begin working on machine learning projects. You do not need to follow the traditional process of manually bringing together separate tools and workflows.

 

The other response options are incorrect because:

- Amazon Textract is a machine learning service that automatically extracts text and data from scanned documents.
- Amazon Lex is a service that enables you to build conversational interfaces using voice and text.
- AWS DeepRacer is an autonomous 1/18 scale race car that you can use to test reinforcement learning models.

**Learn more:**

- [Amazon SageMaker](https://aws.amazon.com/sagemaker)

In Module 9, you learned about the following concepts:

- **The AWS Cloud Adoption Framework**
- **The six strategies for migration**
  - rehost, replatform, repurchase, refactor, retire, retain
- **The AWS Snow Family**
  - how to move massive amounts of data without going over network
  - useful to side step any thru put issues, and is actually more secure then using high speed internet
- Innovation with AWS services

## Additional resources

To learn more about the concepts that were explored in Module 9, review these resources.

- [Migration & Transfer on AWS](https://aws.amazon.com/products/migration-and-transfer)
- [A Process for Mass Migrations to the Cloud](https://aws.amazon.com/blogs/enterprise-strategy/214-2/)
- [6 Strategies for Migrating Applications to the Cloud](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/)
- [AWS Cloud Adoption Framework](https://aws.amazon.com/professional-services/CAF/)
- [AWS Fundamentals: Core Concepts](https://aws.amazon.com/getting-started/fundamentals-core-concepts/)
- [AWS Cloud Enterprise Strategy Blog](https://aws.amazon.com/blogs/enterprise-strategy/)
- [Modernizing with AWS Blog](https://aws.amazon.com/blogs/modernizing-with-aws/)
- [AWS Customer Stories: Data Center Migration](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc|product%23api-gateway|product%23cloudfront|product%23route53|product%23directconnect|product%23elb&awsf.customer-references-category=category%23datacenter-migration)

## Quiz

**<u>Which Perspective of the AWS Cloud Adoption Framework helps you structure the selection and implementation of permissions?</u>**

The correct response option is **Security Perspective**.

**The Security Perspective of the AWS Cloud Adoption Framework also helps you to identify areas on non-compliance and plan ongoing security initiatives.**

The other response options are incorrect because:

- The **Governance Perspective** helps you to <u>identify and implement best practices for IT governance and support business processes with technology</u>.
- The **Operations Perspective** focuses on <u>operating and recovering IT workloads</u> to meet the requirements of your business stakeholders.
- The Business Perspective helps you to move from a model that separates business and IT strategies into a business model that integrates IT strategy.

**Learn more:**

- [Whitepaper: An Overview of the AWS Cloud Adoption Framework](https://d1.awsstatic.com/whitepapers/aws_cloud_adoption_framework.pdf)

---

Which strategies are included in the six strategies for application migration? (Select TWO.)The two correct response options are:

- **Retaining**
- **Rehosting**

The application migration strategies are rehosting, replatforming, refactoring/re-architecting, repurchasing, retaining, and retiring.

---

<u>**What is the storage capacity of AWS Snowmobile?**</u>

100 PB

AWS Snowmobile is a service that is used for transferring up to 100 PB of data to AWS. Each Snowmobile is a 45-foot long shipping container that is pulled by a semi trailer truck.

---

<u>**Which statement best describes Amazon Lex?**</u>

The correct response option is **Amazon Lex**.

 In Amazon Lex, you can quickly build, test, and deploy conversational chatbots to use in your applications.

The other response options are incorrect because:

- A machine learning service that automatically extracts text and data from scanned document describes *Amazon Textract*.
- A document database service that supports MongoDB workloads describes *Amazon DocumentDB*.
- A service that enables you to identify potentially fraudulent online activities describes *Amazon Fraud Detector*.
- 