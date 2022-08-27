5/26/22

# Module 8: Pricing and Support

## ** Learning objectives**

In this module, you will learn how to:

- Describe **AWS pricing and support models**.
- Describe the **AWS Free Tier.**
- Describe **key benefits of AWS Organizations and consolidated billing**.
- Explain the benefits of **AWS Budgets**.
- Explain the benefits of **AWS Cost Explorer**.
- Explain the primary benefits of the **AWS Pricing Calculator**.
- Distinguish between the various **AWS Support Plans.**
- Describe the benefits of **AWS Marketplace**.

---

## AWS Free Tier

- Always free
- 12 months free for service
- Trials

**AWS Lambda** - serverless compute service - allows for 1 million free invocations per month. - this free tier never expires

**Amazon S3** - is free for 12 months for up to 5GB of standard storage, great for trying out website

**AWS Lightsail** - offers 1 month trial of up to 750 hours of usage, ex. deploy and test wordpress blog

![image-20220526190639135](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526190639135.png)

60 or so services

The [AWS Free Tier](https://aws.amazon.com/free/) enables you to begin using certain services without having to worry about incurring costs for the specified period. 

Three types of offers are available: 

- Always Free
- 12 Months Free
- Trials

For each free tier offer, make sure to review the specific details about exactly which resource types are included. 

To learn more, select the **+** symbol next to each category.

**<u>Always Free</u>**

–

These offers do not expire and are available to all AWS customers.



For example, <u>AWS Lambda allows 1 million free requests and up to 3.2 million seconds of compute time per month</u>. <u>Amazon DynamoDB allows 25 GB of free storage per month</u>.

**<u>12 Months Free</u>**

–

These offers are free for 12 months following your initial sign-up date to AWS.



Examples include <u>specific amounts of Amazon S3 Standard Storage</u>, <u>thresholds for monthly hours of Amazon EC2 compute time</u>, and a<u>mounts of Amazon CloudFront data transfer ou</u>t.

**<u>Trials</u>**

–

Short-term free trial offers start from the date you activate a particular service. The length of each trial might vary by number of days or the amount of usage in the service.



For example, <u>Amazon Inspector offers a 90-day free trial</u>. <u>Amazon Lightsail (a service that enables you to run virtual private servers) offers 750 free hours of usage over a 30-day period</u>.

---

The AWS Free Tier includes offers that are available to new AWS customers for a certain period of time following their AWS sign-up date. What is the duration of this period?

The correct response option is **12 months**. 

The AWS Free Tier consists of three types of offers that allow customers to use AWS services without incurring costs: Always free, 12 months free, and Trials.

<u>For 12 months after you first sign up for an AWS account</u>, you can take advantage of offers in the **12 Months Free** category. Examples of offers in this category include specific amounts of Amazon S3 Standard Storage, thresholds for monthly hours of Amazon EC2 compute time, and amounts of Amazon CloudFront data transfer out.



**Learn more:**

- [AWS Free Tier](https://aws.amazon.com/free)

---

## AWS Pricing Concepts

### **How AWS pricing works**

AWS offers a range of cloud computing services with pay-as-you-go pricing. 

To learn more, select the **+** symbol next to each category.

==**Pay for what you use.**==

–

For each service, you pay for exactly the amount of resources that you actually use, without requiring long-term contracts or complex licensing. 



**==Pay less when you reserve.==**

–

Some services offer reservation options that provide a significant discount compared to On-Demand Instance pricing.



For example, suppose that your company is using Amazon EC2 instances for a workload that needs to run continuously. You might choose to run this workload on <u>**Amazon EC2 Instance Savings Plans**, because the plan allows you to save up to 72% over the equivalent On-Demand Instance capacity.</u>

==**Pay less with volume-based discounts when you use more.**==

–

**Some services offer tiered pricing, so the per-unit cost is incrementally lower with increased usage**.



For example, the more Amazon S3 storage space you use, the less you pay for it per GB.

### ***\*AWS Pricing Calculator\****

The [**AWS Pricing Calculator**](https://calculator.aws/#/) lets you explore AWS services and c<u>reate an estimate for the cost of your use cases on AWS</u>. You can <u>organize your AWS estimates by groups that you define</u>. A group can <u>reflect how your company is organized, such as providing estimates by cost center</u>.

When you have created an estimate, you can save it and generate a link to share it with others.

![AWS Pricing Calculator estimate configuration page for Amazon EC2 shows settings for the Region, quick estimate or advanced estimage, and EC2 instance specifications](Module%208%20-%20Pricing%20and%20Support.assets/1RfCTuoWrymHBnb2_X5vopv9JVIgw0bG3.jpg)

Suppose that your company is interested in using Amazon EC2. However, you are not yet sure which AWS Region or instance type would be the most cost-efficient for your use case. **In the AWS Pricing Calculator, you can enter details such as the kind of operating system you need, memory requirements, and input/output (I/O) requirements.** By using the AWS Pricing Calculator, <u>you can review an estimated comparison of different EC2 instance types across AWS Regions.</u>

### **AWS pricing examples**

This section presents a few examples of pricing in AWS services. 

### ==**AWS Lambda**==

To learn more about [AWS Lambda pricing](https://aws.amazon.com/lambda/pricing/), select each tab.

[AWS LAMBDA PRICING](https://assets.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1653613200/YfJS3gyi5GAMP75usT1naQ/tincan/31d9c0cca79c54bdceaf3e938fd424e97c98c7e8/index.html?enhanced_signature=2e50OKklxjxMWmeDpC_sqlYExCvKjH94vz7g6ALIsuQ&endpoint=https%3A%2F%2Fassets.skillbuilder.aws%2Flrs-api%2F&auth=Basic LzFlN2MyY2QzLTNjNGUtNDE1ZS05M2VjLWUwODkyYTNkN2ExYTokMnkkMTMkV2xDOVhVbjNJSjV0V1ZDOWRCL3R1LlNkMEtrRklTWTQ3QkI5Q2hJZjhKSHltbC5rTVhOMzY%3D&actor={"mbox"%3A"mailto%3Ajtoahacoding%40gmail.com"%2C"name"%3A"Jamila+Toaha"}&registration=045803a5-a821-4e91-bd09-009132e65ab8&activity_id=http%3A%2F%2FeMs3fVuk5fRrdzRW22BTIyGPEJ5VTs6k_rise&Accept-Language=en&course_id=134&content_token=045803a5-a821-4e91-bd09-009132e65ab8&session_context=lms&host=explore.skillbuilder.aws&course_code=DIG-BF-100-CECPEB-10-EN&course_id=134&username=1e7c2cd3-3c4e-415e-93ec-e0892a3d7a1a&user_id=1290942&hash=8ca2a47208fb9589b035bc24c1243b44b482e025fc8e11883d574e5d5bbee8cd#)

For AWS Lambda, you are charged based on the number of requests for your functions and the time that it takes for them to run.

**AWS Lambda allows 1 million free requests and up to 3.2 million seconds of compute time per month.**

You can save on AWS Lambda costs by signing up for **Compute Savings Plans**. Compute Savings Plans <u>offer lower compute costs in exchange for committing to a consistent amount of usage over a 1-year or 3-year term</u>. This is an example of **paying less when you reserve**. 

<u>PRICING EXAMPLE</u>

If you have used AWS Lambda in multiple AWS Regions, you can view the itemized charges by Region on your bill. 

In this example, all the AWS Lambda usage occurred in the Northern Virginia Region. The bill lists separate charges for the number of requests for functions and their duration. 

Both the number of requests and the total duration of requests in this example are under the thresholds in the AWS Free Tier, so the account owner would not have to pay for any AWS Lambda usage in this month.

![Example of service charges for AWS Lambda](Module%208%20-%20Pricing%20and%20Support.assets/F2z0xKaA-pT10idO_vBX82XA7yd3QXpgS.png)

### **Amazon EC2**

To learn more about [Amazon EC2 pricing](https://aws.amazon.com/ec2/pricing/), select each tab.

<u>AMAZON EC2 PRICING</u>

**With Amazon EC2, you pay for only the compute time that you use while your instances are running.**

For some workloads, you can significantly reduce Amazon EC2 costs by using S**pot Instances**. For example, suppose that you are running a batch processing job that is able to withstand interruptions. ==Using a Spot Instance would provide you with up to 90% cost savings while still meeting the availability requirements of your workload.==

You can find additional cost savings for Amazon EC2 by considering Savings Plans and Reserved Instances.

<u>PRICING EXAMPLE</u>

The service charges in this example include details for the following items:

- Each Amazon EC2 instance type that has been used
- The amount of Amazon EBS storage space that has been provisioned
- The length of time that Elastic Load Balancing has been used

In this example, all the usage amounts are under the thresholds in the AWS Free Tier, so the account owner would not have to pay for any Amazon EC2 usage in this month.

![Example of service charges for Amazon EC2](Module%208%20-%20Pricing%20and%20Support.assets/16t1PXx-SEeaSpYF_P8TO97KQwkScisje.png)

### **Amazon S3**

To learn more about [Amazon S3 pricing](https://aws.amazon.com/s3/pricing/), select each tab.

<u>AMAZON S3 PRICING</u>

For Amazon S3 pricing, consider the following cost components:

- **Storage -** <u>You pay for only the storage that you use.</u> You are charged the rate to store objects in your Amazon S3 buckets based on your <u>objects’ sizes, storage classes, and how long you have stored each object during the mont</u>h.
- **Requests and data retrievals -** <u>You pay for requests made to your Amazon S3 objects and buckets.</u> For example, suppose that you are storing photo files in Amazon S3 buckets and hosting them on a website. Every time a visitor requests the website that includes these photo files, this counts towards requests you must pay for.
- **Data transfer -** There is <u>no cost to transfer data between different Amazon S3 buckets or from Amazon S3 to other services within the same AWS Region.</u> However, <u>you pay for data that you transfer into and out of Amazon S3</u>, with a few exceptions. There is <u>no cost for data transferred into Amazon S3 from the internet or out to Amazon CloudFron</u>t. There is also no cost for data transferred out to an Amazon EC2 instance in the same AWS Region as the Amazon S3 bucket.
- **Management and replication -** You <u>pay for the storage management features</u> that you have enabled on your account’s Amazon S3 buckets. These features include Amazon S3 inventory, analytics, and object tagging.

<u>PRICING EXAMPLE</u>

The AWS account in this example has used Amazon S3 in two Regions: Northern Virginia and Ohio. For each Region, itemized charges are based on the following factors:

- The number of requests to add or copy objects into a bucket
- The number of requests to retrieve objects from a bucket
- The amount of storage space used

All the usage for Amazon S3 in this example is under the AWS Free Tier limits, so the account owner would not have to pay for any Amazon S3 usage in this month.

![Example of service charges for Amazon S3](Module%208%20-%20Pricing%20and%20Support.assets/Vb0cDUMcQ0HfuKj__GC9mP13u89WV16--.png)

---

## Billing Dashboard



![image-20220526193714318](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526193714318.png)

![image-20220526193724701](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526193724701.png)

![image-20220526193744511](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526193744511.png)

- broken down by region and even global services are broken down

Use the [**AWS Billing & Cost Management dashboard**](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-what-is.html) to pay your AWS bill, monitor your usage, and analyze and control your costs.

- **Compare your current month-to-date balance with the previous month**, **and get a forecast** of the next month based on current usage.
- **View month-to-date** spend by service.
- **View Free Tier** usage by service.
- **Access Cost Explorer** and create budgets.
- Purchase and manage **Savings Plans.**
- Publish [AWS Cost and Usage Reports](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html).

---

## Consolidated Billing

==AWS Organizations - Consolidated Billing - Roll AWS bills into one bill owned by the owner of the organization==

- makes it easier to keep track
- view in one place
- AWS offers bulk pricing, even if one service is used only a little, but aggregate use counts

![image-20220526194303496](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526194303496.png)

Sounds nice to me, considering how big the bill is gonna be  0:)




![Example of charges from multiple accounts in a single consolidated bill](Module%208%20-%20Pricing%20and%20Support.assets/HI0T5D1NZvjPQ8HY_jH79KVaz8BCgDsQ9.png)

Each month, **AWS charges your primary payer account for all the linked accounts in a consolidated bill.** Through the primary account, you can also get a detailed cost report for each linked account. 

The monthly consolidated bill also **includes the account usage costs incurred by the primary account**. This cost is not a premium charge for having a primary account. 

The consolidated bill shows the costs associated with any actions of the primary account (such as storing files in Amazon S3 or running Amazon EC2 instances).

### Example: Consolidated billing

To review an example of consolidated billing, select **Start**. 

START 

<u>Step 1</u>

![Diagram of three AWS accounts managed through a single organization](Module%208%20-%20Pricing%20and%20Support.assets/5rFGnoWuTIOlHvUk_n_FMIV9Ltf50FVhc.png)

Suppose that you are the business leader who oversees your company’s AWS billing. 

Your company has three AWS accounts used for separate departments. Instead of paying each location’s monthly bill separately, you decide to create an organization and add the three accounts. 

You manage the organization through the primary account.



<u>Step 2</u>

![Example of charges from multiple accounts in a single consolidated bill](Module%208%20-%20Pricing%20and%20Support.assets/HI0T5D1NZvjPQ8HY_jH79KVaz8BCgDsQ9-20220526194707836.png)

Each month, AWS charges your primary payer account for all the linked accounts in a consolidated bill. Through the primary account, you can also get a detailed cost report for each linked account. 

The monthly consolidated bill also includes the account usage costs incurred by the primary account. This cost is not a premium charge for having a primary account. 

The consolidated bill shows the costs associated with any actions of the primary account (such as storing files in Amazon S3 or running Amazon EC2 instances).

<u>Step 3</u>

![Example of three separate AWS accounts with separate amounts of Amazon S3 usage](Module%208%20-%20Pricing%20and%20Support.assets/dFd5Q4YhZsH557tn_rFlBeqGAW7Kc09C2.png)

Consolidated billing also enables you to share volume pricing discounts across accounts. 

Some AWS services, such as Amazon S3, provide volume pricing discounts that give you lower prices the more that you use the service. In Amazon S3, after customers have transferred 10 TB of data in a month, they pay a lower per-GB transfer price for the next 40 TB of data transferred. 

In this example, there are three separate AWS accounts that have transferred different amounts of data in Amazon S3 during the current month: 

- Account 1 has transferred 2 TB of data.
- Account 2 has transferred 5 TB of data.
- Account 3 has transferred 7 TB of data.



Because no single account has passed the 10 TB threshold, none of them is eligible for the lower per-GB transfer price for the next 40 TB of data transferred.

## AWS Budgets

==**AWS Budgets** - allows you to set custom budges for a variety of scenarioes like cost and usage==

- you will then receive alerts when costs have exceeed or about to (80% for example) exceed budgeted amount

![image-20220526195019561](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526195019561.png)

- go to billing section 
- ![image-20220526195055078](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526195055078.png)
- ![image-20220526195112590](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526195112590.png)
- ![image-20220526195133211](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526195133211.png)

### **AWS Budgets**

==In [**AWS Budgets**](https://aws.amazon.com/aws-cost-management/aws-budgets), you can create budgets to plan your service usage, service costs, and instance reservations.==

The information in AWS Budgets <u>updates three times a day.</u> This helps you to accurately determine how close your usage is to your budgeted amounts or to the AWS Free Tier limits.

In AWS Budgets, you can also <u>set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.</u>

### **Example: AWS Budgets**

Suppose that you have set a budget for Amazon EC2. You want to ensure that your company’s usage of Amazon EC2 does not exceed $200 for the month. 

In AWS Budgets, you could set a custom budget to notify you when your usage has reached half of this amount ($100). This setting would allow you to receive an alert and decide how you would like to proceed with your continued use of Amazon EC2.

To learn more, select each marker.

![image-20220526195252036](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526195252036.png)

---

## AWS Cost Explorer

AWS has a variable cost model and you pay for what you use. 

AWS Cost Explorer - console-based service allows you to visually see

- gives you 12 months of historical data

![image-20220526195632182](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526195632182.png)

![image-20220526195642675](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526195642675.png)

![image-20220526195653031](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526195653031.png)

many resources are taggable - tags - user defined

![image-20220526195720549](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526195720549.png)

### **AWS Cost Explorer**

==[**AWS Cost Explorer**](https://aws.amazon.com/aws-cost-management/aws-cost-explorer/) is a tool that enables you to visualize, understand, and manage your AWS costs and usage over time.==

**AWS Cost Explorer includes a default report of the costs and usage for your top five cost-accruing AWS services.** You can apply <u>custom filters and groups</u> to analyze your data. For example, you can view resource usage at the hourly level.

### **Example: AWS Cost Explorer**

![Example of the AWS Cost Explorer dashboard, displaying monthly costs for Amazon EC2 instances over a 6-month period](Module%208%20-%20Pricing%20and%20Support.assets/p0pzjH7LAaeNG9O1_pS6DLACY5OOiDZZb.png)

This example of the AWS Cost Explorer dashboard displays monthly costs for Amazon EC2 instances over a 6-month period. <u>The bar for each month separates the costs for different Amazon EC2 instance types (such as t2.micro or m3.large).</u> 

**By analyzing your AWS costs over time, you can make informed decisions about future costs and how to plan your budgets.**

----

## AWS Support Plans

![image-20220526201537671](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526201537671.png)

- free for everyone

As you begin to move into high levels of mission critical projects, AWS offers higher level of support:

- ![image-20220526201644580](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526201644580.png)
- response of less than 12 hours in case your systems are impaired
- great tier for businesses experimenting, and setting up tests

![image-20220526201756886](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526201756886.png)

![image-20220526201812070](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526201812070.png)

- brand new launches or global advertising

![image-20220526201843029](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526201843029.png)

- **TAM** - part of concierge support team that comes with enterprise level support
  - specialize in not only proactively monitoring your environment and assisting with optimzations, but also provide infrastructure management, well-architected reviews and operations reviews 
  - well-architected reviews - reviewed against 5 principles
- ![image-20220526201915680](Module%208%20-%20Pricing%20and%20Support.assets/image-20220526201915680.png)

https://aws.amazon.com/premiumsupport

### **AWS Support**

AWS offers four different [**Support plans**](https://aws.amazon.com/premiumsupport/plans/) to help you troubleshoot issues, lower costs, and efficiently use AWS services. 

==You can choose from the following Support plans to meet your company’s needs:==

- Basic
- Developer
- Business
- Enterprise

### **Basic Support**

**Basic Support** is free for all AWS customers. It includes access to <u>whitepapers, documentation, and support communities</u>. With Basic Support, you can also contact AWS for <u>billing questions and service limit increases</u>.

With Basic Support, you have access to a <u>limited selection of AWS Trusted Advisor checks</u>. Additionally, you can use the **AWS Personal Health Dashboard**, a tool that provides alerts and remediation guidance when AWS is experiencing events that may affect you. 

If your company needs support beyond the Basic level, you could consider purchasing Developer, Business, or Enterprise Support.

### **Developer, Business, and Enterprise Support**

The Developer, Business, and Enterprise Support plans include all the benefits of Basic Support, in addition to the ability to <u>open an unrestricted number of technical support cases</u>. These three Support plans have pay-by-the-month pricing and require no long-term contracts.

The information in this course highlights only a selection of details for each Support plan. A complete overview of what is included in each Support plan, including pricing for each plan, is available on the [AWS Support](https://aws.amazon.com/premiumsupport/plans/) site.

In general, for pricing, the Developer plan has the lowest cost, the Business plan is in the middle, and the Enterprise plan has the highest cost. 

To learn more, select the **+** symbol next to each category.

**Developer Support**

–

Customers in the **Developer Support** plan have access to features such as:

- Best practice guidance
- Client-side diagnostic tools
- Building-block architecture support, which consists of guidance for how to use AWS offerings, features, and services together

For example, suppose that your company is exploring AWS services. You’ve heard about a few different AWS services. However, you’re unsure of how to potentially use them together to build applications that can address your company’s needs. In this scenario, the <u>building-block architecture support</u> that is included with the Developer Support plan could help you to identify opportunities for combining specific services and features.

**Business Support**

–

Customers with a **Business Support** plan have access to additional features, including: 

- <u>Use-case guidance</u> to identify AWS offerings, features, and services that can best support your specific needs
- <u>All AWS Trusted Advisor checks</u>
- Limited support for third-party software, such as common operating systems and application stack components

Suppose that your company has the Business Support plan and wants to install a common third-party operating system onto your Amazon EC2 instances. You could contact AWS Support for assistance with installing, configuring, and troubleshooting the operating system. For advanced topics such as optimizing performance, using custom scripts, or resolving security issues, you may need to contact the third-party software provider directly.

**Enterprise Support**

–

In addition to all the features included in the Basic, Developer, and Business Support plans, customers with an **Enterprise Support** plan have access to features such as:

- Application architecture guidance, which is a consultative relationship to support your company’s specific use cases and applications
- <u>Infrastructure event management:</u> A short-term engagement with AWS Support that helps your company gain a better understanding of your use cases. This also provides your company with architectural and scaling guidance.
- A <u>Technical Account Manager</u>

### **Technical Account Manager (TAM)**

The Enterprise Support plan includes access to a **Technical Account Manager (TAM)**.

If your company has an Enterprise Support plan, <u>the TAM is your primary point of contact at AWS</u>. T<u>hey provide guidance, architectural reviews, and ongoing communication with your company</u> as you plan, deploy, and optimize your applications. 

Your TAM provides expertise across the full range of AWS services. They help you <u>design solutions that efficiently use multiple services together through an integrated approach</u>.

For example, suppose that you are interested in developing an application that uses several AWS services together. Your TAM could provide insights into how to best use the services together. They achieve this, while aligning with the specific needs that your company is hoping to address through the new application.

Which Support plan includes all AWS Trusted Advisor checks at the lowest cost?



Basic

Correctly unselected



Developer

Correctly unselected



Business

Correctly selected



Enterprise

Correctly unselected

SUBMIT

Correct

The correct response option is **Business**.

 

Only the Business and Enterprise Support plans include all AWS Trusted Advisor checks. Of these two Support plans, the Business Support plan has a lower cost.



**Learn more:**

- [Compare AWS Support plans](https://aws.amazon.com/premiumsupport/plans/)

---

## AWS Marketplace

**AWS Marketplace** is a curated digital catalog that streamlines your steps to find, deploy and manage <u>third party software</u> running in your AWS architecture, all while providing a range of payment options

- AWS Marketplace - customers have options like 1 click deployment
- almost any vendor will allow you to use existing license.
- Most vendors offers 'pay-as-you-go' options
- Marketplace has Enterprise-focused features
  - Customer terms and pricing
  - private marketplace - custom catalog for software that meets your legal and security requirements
  - integration into your procurement systems
  - cost management tools

==**https://aws.amazon.com/marketplace**==

==[**AWS Marketplace**](https://aws.amazon.com/marketplace) is a digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS.== 

For each listing in AWS Marketplace, you can access detailed information on pricing options, available support, and reviews from other AWS customers.

You can also explore software solutions by industry and use case. For example, suppose that your company is in the healthcare industry. In AWS Marketplace, you can review use cases that software helps you to address, such as implementing solutions to protect patient records or using machine learning models to analyze a patient’s medical history and predict possible health risks.

### **AWS Marketplace categories**

![Icons to represent each AWS Marketplace category: Business Applications, Data and Analytics, DevOps, Infrastructure Software, Internet of Things (IoT), Machine Learning, Migration, and Security](Module%208%20-%20Pricing%20and%20Support.assets/dm8r2ZR44V96NBWg_JnfverlpKFgd2aCe.png)

AWS Marketplace offers products in several categories, such as Infrastructure Products, Business Applications, Data Products, and DevOps.

Within each category, you can narrow your search by browsing through product listings in subcategories. For example, subcategories in the DevOps category include areas such as Application Development, Monitoring, and Testing.

In Module 8, you learned about the following concepts:

- Three types of offers included in the AWS Free Tier: 12 months free, Always free, and Trials
- Benefits of consolidated billing in AWS Organizations
- Tools for planning, estimating, and reviewing AWS costs
- Differences between the four AWS Support plans: Basic, Developer, Business, and Enterprise
- How to discover software in AWS Marketplace

![Screen Shot 2022-05-30 at 9.41.30 PM](Module%208%20-%20Pricing%20and%20Support.assets/Screen%20Shot%202022-05-30%20at%209.41.30%20PM.png)

## **Additional resources**

To learn more about the concepts that were explored in Module 8, review these resources.

- [AWS Pricing](https://aws.amazon.com/pricing)
- [AWS Free Tier](https://aws.amazon.com/free)
- [AWS Cost Management](https://aws.amazon.com/aws-cost-management/)
- [Whitepaper: How AWS Pricing Works](https://docs.aws.amazon.com/whitepapers/latest/how-aws-pricing-works/welcome.html)
- [Whitepaper: Introduction to AWS Economics](https://d1.awsstatic.com/whitepapers/introduction-to-aws-cloud-economics-final.pdf)
- [AWS Support](https://aws.amazon.com/premiumsupport)
- [AWS Knowledge Center](https://aws.amazon.com/premiumsupport/knowledge-center/)

## Quiz

---

<u>**Which action can you perform with consolidated billing?**</u>

The correct response option is: **Combine usage across accounts to receive volume pricing discounts**.

 

The other response options are incorrect because:

- Review how much cost your predicted AWS usage will incur by the end of the month - You can perform this action in *AWS Budgets*.
- Create an estimate for the cost of your use cases on AWS - You can perform this action in *AWS Pricing Calculator*.
- Visualize and manage your AWS costs and usage over time - You can perform this action in *AWS Cost Explorer*.

**Learn more:**

- [Consolidated billing for AWS Organizations](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/consolidated-billing.html)

---

<u>**Which pricing tool is used to visualize, understand, and manage your AWS costs and usage over time?**</u>

The correct response option is **AWS Cost Explorer**.

 

**AWS Cost Explorer includes a default report of the costs and usage for your top five cost-accruing AWS services**. You can apply custom filters and groups to analyze your data. For example, you can view resource usage at the hourly level.

 

The other response options are incorrect because:

- AWS Pricing Calculator enables you to create an estimate for the cost of your use cases on AWS.
- AWS Budgets enables you to create budgets to plan your service usage, service costs, and instance reservations. In AWS Budgets, you can also set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.
- The AWS Free Tier is a program that consists of three types of offers that allow customers to use AWS services without incurring costs: Always free, 12 months free, and Trials.

---

**<u>Which pricing tool enables you to receive alerts when your service usage exceeds a threshold that you have defined?</u>**

The correct response option is **AWS Budgets**.

In AWS Budgets, you can set custom alerts that will notify you when your service usage exceeds (or is forecasted to exceed) the amount that you have budgeted.

**Your budget can be based on costs or usage.** For example, you can set an alert that will notify you when you have incurred $100.00 of costs in Amazon EC2 or 500,000 requests in AWS Lambda.

 

The other response options are incorrect because:

- From the billing dashboard in the AWS Management Console, you can view details on your AWS bill, such as service costs by Region, month to date spend, and more. However, you cannot set alerts from the billing dashboard.
- The AWS Free Tier is a program that consists of three types of offers that allow customers to use AWS services without incurring costs: Always free, 12 months free, and Trials.
- AWS Cost Explorer is a tool that enables you to visualize, understand, and manage your AWS costs and usage over time.

**Learn more:**

- [AWS Budgets](https://aws.amazon.com/aws-cost-management/aws-budgets)

---

**<u>Your company wants to receive support from an AWS Technical Account Manager (TAM). Which support plan should you choose?</u>**

The correct response option is **Enterprise**.

A Technical Account Manager (TAM) is available only to AWS customers with an Enterprise Support plan. A TAM provides guidance, architectural reviews, and ongoing communication with your company as you plan, deploy, and optimize your applications.

---

<u>**Which service or resource is used to find third-party software that runs on AWS?**</u>

The correct response option is **AWS Marketplace**.

 

AWS Marketplace is a digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS.

 

The other response options are incorrect because:

- The AWS Free Tier consists of offers that allow customers to use AWS services without incurring costs. These offers are related to AWS services, not third-party software that can be used on AWS.
- AWS Support is a resource that can answer questions about best practices, assist with troubleshooting issues, help you to identify ways to optimize your use of AWS services, and so on.
- You can use the billing dashboard in the AWS Management Console to view details such as service costs by Region, the top services being used by your account, and forecasted billing costs. From the billing dashboard, you can also access other AWS billing tools, such as AWS Cost Explorer, AWS Budgets, and AWS Budgets Reports.

**Learn more:**

- [AWS Marketplace](https://aws.amazon.com/marketplace)