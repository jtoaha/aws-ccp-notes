5/18/22

# Module 6: Security

## **Learning objectives**

In this module, you will learn how to:

- Explain the benefits of the <u>shared responsibility model</u>.
- Describe <u>multi-factor authentication</u> (MFA).
- Differentiate between the <u>AWS Identity and Access Management (IAM)</u> security levels.
- Explain the <u>main benefits of AWS Organizations.</u>
- Describe <u>security policies</u> at a basic level.
- Summarize the <u>benefits of compliance with AWS</u>.
- Explain additional <u>AWS security services</u> at a basic level.

![image-20220518180750294](Module%206%20-%20Security.assets/image-20220518180750294-2911690.png)

- AWS controls the data centers, security of  services, and all the layers in this section
- Workloads that customers run in the cloud and are responsible for

## **Shared responsibility model**

When it comes to securing business, who is responsible? both AWS and the customer

- Environment is not a single object, but rather a collection
  - AWS responsible for some of the parts, and other parts the customer is responsible for



### EC2 lives in physical data center

![image-20220518181158063](Module%206%20-%20Security.assets/image-20220518181158063.png)

- **Operating System** - AWS does not have any backdoor into your system, you alone have the only encryption key to log into the root of this OS or to create any user accounts there
  - AWS cannot enter your operating system
  - If someone from AWS calls and asks for your operating key, it is not AWS
  - This means that the customer is 100 % responsible for keeping the Operating System patched, if AWS discovers vulnerabilities, they can notify owner, but it cannot deploy a patch
  - This means no one can deploy anything that might break your system without your team being the ones that do it. 
- **Your Data** - This is your domain you can control who can see it, whether public or private, depending on your use case. You can even lock down. 
  - ability to have ubiquitous encryption. That way all people can see is encrypted content. 

## **The AWS shared responsibility model**

Throughout this course, you have learned about a variety of resources that you can create in the AWS Cloud. These resources include <u>Amazon EC2 instances, Amazon S3 buckets, and Amazon RDS databases.</u> Who is responsible for keeping these resources secure: you (the customer) or AWS?

The answer is both. The reason is that you do not treat your AWS environment as a single object. <u>Rather, you treat the environment as a collection of parts that build upon each other.</u> AWS is responsible for some parts of your environment and you (the customer) are responsible for other parts. This concept is known as the [**shared responsibility model**](https://aws.amazon.com/compliance/shared-responsibility-model/).

==The shared responsibility model divides into **customer responsibilities** (commonly referred to as “security in the cloud”) and **AWS responsibilities** (commonly referred to as “security of the cloud”).==

![image-20220518181821125](Module%206%20-%20Security.assets/image-20220518181821125.png)

You can think of this model as being similar to the division of responsibilities between a homeowner and a homebuilder. The builder (AWS) is responsible for constructing your house and ensuring that it is solidly built. As the homeowner (the customer), it is your responsibility to secure everything in the house by ensuring that the doors are closed and locked. 

To learn more, select the **+** symbol next to each category.

==Customers: Security in the cloud==

–

<u>Customers are responsible for the security of everything that they create and put *in* the AWS Cloud</u>.



When using AWS services, you, the customer, maintain complete control over your content. You are responsible for managing <u>security requirements for your content</u>, including which content you choose to store on AWS, which AWS services you use, and <u>who has access</u> to that content. You also control h<u>ow access rights are granted, managed, and revoked</u>.

 

The security steps that you take will depend on factors such as the services that you use, the complexity of your systems, and your company’s specific operational and security needs. Steps include <u>selecting, configuring, and patching the operating systems that will run on Amazon EC2 instances, configuring security groups, and managing user accounts</u>. 

==AWS: Security of the cloud==

–

AWS is responsible for security *of* the cloud.

 

<u>AWS operates, manages, and controls the components at all layers of infrastructure.</u> This includes areas such as the <u>host operating system, the virtualization layer, and even the physical security of the data centers</u> from which services operate. 

 

AWS is responsible for <u>protecting the global infrastructure</u> that runs all of the services offered in the AWS Cloud. This infrastructure includes <u>AWS Regions, Availability Zones, and edge location</u>s.

 

AWS manages the <u>security of the cloud, specifically the physical infrastructure that hosts your resources</u>, which include:

- Physical security of data centers
- Hardware and software infrastructure
- Network infrastructure
- Virtualization infrastructure

Although you cannot visit AWS data centers to see this protection firsthand, AWS provides several reports from third-party auditors. These auditors have verified its compliance with a variety of computer security standards and regulations.

---

**Which tasks are the responsibilities of customers? (Select TWO.)**

- 

  Maintaining network infrastructure

  Correctly unchecked

- 

  Patching software on Amazon EC2 instances

  Correctly checked

- 

  Implementing physical security controls at data centers

  Correctly unchecked

- 

  Setting permissions for Amazon S3 objects

  Correctly checked

- 

  Maintaining servers that run Amazon EC2 instances

  Correctly unchecked

SUBMIT

Correct

The correct two response options are:

- **Patching software on Amazon EC2 instances**
- **Setting permissions for Amazon S3 objects**

The other three response options are tasks that are the responsibility of AWS.



**Learn more:**

- [AWS shared responsibility model](https://aws.amazon.com/compliance/shared-responsibility-model/)

---

## User permissions and access

When you create AWS account, you are given <u>AWS account root user</u>:

==**AWS account root user**==: access and control any resource in the account

- spin up databases, EC2 instances, blockchain services, etc
- as soon as you create this, it is recommended to turn on multi-facor authentication or MFA, so you to make you need a randomized token to login
- even with MFA turned on, you don't want to use root user for everything

![image-20220518182720477](Module%206%20-%20Security.assets/image-20220518182720477.png)

- You can control in a granular way with ==**AWS Identity and Access Management** (AWS IAM)==

- When you create an IAM user by default it has no permissions, the user can't even log into the AWS account at first

  - It has absolutely zero permission, just be given explicit permission  for any action for any user

  - ==**Principle of least privilege:** A user is granted access only to what is needed==

  - You associate an IAM policy to an IAM user

    - **IAM policy** - JSON document that describes the calls a user can and can not make

      ![image-20220518183100906](Module%206%20-%20Security.assets/image-20220518183100906.png)

      - If policy is attached to user, can only view coffee_shop_reports
      - **There are only 2 potential options for "Effect" on any policy: "Allow" or "Deny"**
      - **For "Action", you can list any AWS API call**
      - **For "Resource", list which AWS resource that API call is for**

  - As a business person, you wouldn't need to write these policies, but they are all over AWS

  - One way to make it easier to manage user and their permissions is to organize them into <u>IAM groups</u> (groupings of users)

    - you can attach a policy to that group and each user in that group will get permission
      - ex. users in cashier group getting permission, instead of individual users getting permission directly, this way easier to manage

**<u>AWS identities in AWS IAM:</u>** Root user, users, groups, policies, roles

![image-20220518183730617](Module%206%20-%20Security.assets/image-20220518183730617.png)

- Roles - sometimes a user's role at work changes and is temp in nature, so you can create 'Roles'
- ![image-20220518183908971](Module%206%20-%20Security.assets/image-20220518183908971.png)
- ![image-20220518183920914](Module%206%20-%20Security.assets/image-20220518183920914.png)
- **When an identity assumes a role, it abandons all the previous permissions it has, and assumes the permissions of hte role.** 
- <u>You can avoid creating IAM users by federating users into your account</u>
  - they can use their regular corporate credentials to log in to AWS by mapping corporate identities to IAM roles

==AWS IAM authentication and authorization as a service.==

### **AWS Identity and Access Management (IAM)**

==[**AWS Identity and Access Management (IAM)**](https://aws.amazon.com/iam/) enables you to manage access to AWS services and resources securely.==

<u>IAM gives you the flexibility to configure access based on your company’s specific operational and security needs.</u> You do this by using a combination of IAM features, which are explored in detail in this lesson:

- IAM users, groups, and roles
- IAM policies
- Multi-factor authentication

You will also learn best practices for each of these features.

### **AWS account root user**

When you first create an AWS account, you begin with an identity known as the [**root user**](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html). 

<u>The root user is accessed by signing in with the email address and password that you used to create your AWS account.</u> You can think of the root user as being similar to the owner of the coffee shop. It has complete access to all the AWS services and resources in the account.

![Process diagram of creating and using the AWS account root user](Module%206%20-%20Security.assets/crtCMJS9pAjmecS5_G6mCtOEHNBDNNKV4.png)

Best practice:

==Do **not** use the root user for everyday tasks.==

Instead, <u>use the root user to create your first IAM user</u> and <u>assign it permissions to create other users</u>.

Then, continue to create other IAM users, and access those identities for performing regular tasks throughout AWS. <u>Only use the root user when you need to perform a limited number of tasks that are only available to the root us</u>er. Examples of these tasks include c<u>hanging your root user email address</u> and <u>changing your AWS support plan</u>.

### **IAM users**

==An **IAM user** is an identity that you create in AWS.== It represents the person or application that interacts with AWS services and resources. It consists of a name and credentials.

<u>By default, when you create a new IAM user in AWS, it has no permissions associated with it.</u> To allow the IAM user to perform specific actions in AWS, such as launching an Amazon EC2 instance or creating an Amazon S3 bucket, you must grant the IAM user the necessary permissions.

Best practice:

==We recommend that you create individual IAM users for each person who needs to access AWS==.  

Even if you have multiple employees who require the same level of access, you should create individual IAM users for each of them. This <u>provides additional security by allowing each IAM user to have a unique set of security credentials.</u>

### **IAM policies**

==An **IAM** **policy** is a document that allows or denies permissions to AWS services and resources.==

IAM policies enable you to <u>customize users’ levels of access to resources.</u> For example, you can allow users to access all of the Amazon S3 buckets within your AWS account, or only a specific bucket.

Best practice:

==Follow the security principle of **least privilege** when granting permissions.==

By following this principle, you help to <u>prevent users or roles from having more permissions than needed</u> to perform their tasks. 

For example, i<u>f an employee needs access to only a specific bucket, specify the bucket in the IAM policy</u>. Do this instead of granting the employee access to all of the buckets in your AWS account.

### **Example: IAM policy**

Here’s an example of how IAM policies work. Suppose that the coffee shop owner has to create an IAM user for a newly hired cashier. The cashier <u>needs access to the receipts kept in an Amazon S3 bucket with the ID: AWSDOC-EXAMPLE-BUCKET.</u>

![Example IAM policy](Module%206%20-%20Security.assets/4PUOpE714WIQyBUs_wwEWNhiDL7wyp00S.png)

This example IAM policy <u>allows permission to view a list of objects in the Amazon S3 bucket with ID *awsdoc-example-bucket*</u>, and also access them.

In this example, the IAM policy is allowing specific actions within <u>Amazon S3: ListObject and GetObject</u>. The policy also mentions a specific bucket ID: <u>*awsdoc-example-bucket*</u>. When the owner attaches this policy to the cashier’s IAM user, it will allow the cashier to view a list of the objects in the *awsdoc-example-bucket* bucket and also access them. 

If the owner wants the cashier to be able to access other services and perform other actions in AWS, the owner must attach additional policies to specify these services and actions.

Now, suppose that the coffee shop has hired a few more cashiers. Instead of assigning permissions to each individual IAM user, the owner places the users into an [**IAM group**](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html).

### **IAM groups**

==An **IAM group** is a collection of IAM users. When you assign an IAM policy to a group, all users in the group are granted permissions specified by the policy.==

Here’s an example of how this might work in the coffee shop. <u>Instead of assigning permissions to cashiers one at a time, the owner can create a “Cashiers” IAM group. The owner can then add IAM users to the group and then attach permissions at the group level.</u> 

![Example of three IAM users that have been added into the "Cashiers" IAM group](Module%206%20-%20Security.assets/fzH_Z7auFRkM1pSe_dJWwAFus-2ObBezE.png)

Assigning IAM policies at the group level also <u>makes it easier to adjust permissions when an employee transfers to a different jo</u>b. For example, if a cashier becomes an inventory specialist, the coffee shop owner removes them from the “Cashiers” IAM group and adds them into the “Inventory Specialists” IAM group. <u>This ensures that employees have only the permissions that are required for their current role</u>.

==What if a coffee shop employee hasn’t switched jobs permanently, but instead, rotates to different workstations throughout the day? This employee can get the access they need through [**IAM roles**](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html).==

### **IAM roles**

In the coffee shop, an <u>employee rotates to different workstations throughout the day</u>. Depending on the staffing of the coffee shop, this employee might perform several duties: work at the cash register, update the inventory system, process online orders, and so on. 

When the employee needs to switch to a different task, they give up their access to one workstation and gain access to the next workstation. The employee <u>can easily switch between workstations</u>, <u>but at any given point in time, they can have access to only a single workstation</u>. This same concept exists in AWS with IAM roles.

An IAM role is an identity that you can assume to gain temporary access to permissions.  

Before an IAM user, application, or service can assume an IAM role, they must be granted permissions to switch to the role. <u>When someone assumes an IAM role, they abandon all previous permissions that they had</u> under a previous role and assume the permissions of the new role. 

Best practice:

<u>IAM roles are ideal for situations in which access to services or resources needs to be granted temporarily, instead of long-term.</u>

### **Multi-factor authentication**

Have you ever signed in to a website that required you to provide multiple pieces of information to verify your identity? You might have needed to provide your password and then a second form of authentication, such as a random code sent to your phone. This is an example of [**multi-factor authentication**](https://aws.amazon.com/iam/features/mfa/).

In IAM, multi-factor authentication (MFA) provides an extra layer of security for your AWS account.

1. First, when a **user signs in to an AWS website,** they enter their IAM user ID and password.
2. Next, **the user is prompted for an authentication response from their AWS MFA device.** This device could be a <u>hardware security key, a hardware device, or an MFA application</u> on a device such as a smartphone.

## AWS Organizations

As company grows, it's important to have a seperation of duties. 

Developers - dev resources

Accountants - access billing info

Or even have business units seperated so they can experiment without clashes

==**AWS organizations:** A central location to manage multiple AWS acocunts==

- You can manage different departments across AWS Organization

AWS 

![image-20220518190245570](Module%206%20-%20Security.assets/image-20220518190245570.png)

- **Consolidated billing:** You can use primary account for organization to consolidate and pay for all acounts
  - also bulk discounts

- **Implement hierarchical groupings of accounts**:  You can to meet security, compliance or budgetory needs. you can group accounts into organizational units, or OUs, similar to Business Units, if you need certain departments to access a specific service, you can put those accounts into an OU
- **AWS service and API actions access control:** that each account can access.
  - you can use **service control policies (SCPs)** to pecify the maximum permissions for member accounts in the organization
    - you can restrict which AWS services, resources, and individual API actions, the users and roles in each member account can access.

### **AWS Organizations**

Suppose that your company has multiple AWS accounts. ==You can use [**AWS Organizations**](https://aws.amazon.com/organizations) to consolidate and manage multiple AWS accounts within a central location.==

<u>When you create an organization, AWS Organizations automatically creates a **root**,</u> which is the parent container for all the accounts in your organization. 

I==n AWS Organizations, you can centrally control permissions for the accounts in your organization by using [**service control policies (SCPs)**](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html). **SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.**==

**Consolidated billing** is another feature of AWS Organizations. You will learn about consolidated billing in a later module.

### **Organizational units**

==In AWS Organizations, you can group accounts into **organizational units (OUs)** to make it easier to manage accounts with similar business or security requirements.== When you apply a policy to an OU, a<u>ll the accounts in the OU automatically inherit the permissions specified in the policy</u>.  

**By organizing separate accounts into OUs, you can more easily isolate workloads or applications that have specific security requirements**. For instance, <u>if your company has accounts that can access only the AWS services that meet certain regulatory requirements</u>, you can put these accounts into one OU. Then, <u>you can attach a policy to the OU that blocks access to all other AWS services that do not meet the regulatory requirements</u>.

For example: 

![image-20220518192036083](Module%206%20-%20Security.assets/image-20220518192036083.png)

In designing your organization, you consider the business, security, and regulatory needs of each department. You use this information to decide which departments group together in OUs.

![image-20220518192153993](Module%206%20-%20Security.assets/image-20220518192153993.png)

The finance and IT departments have requirements that do not overlap with those of any other department. <u>You bring these accounts into your organization to take advantage of benefits such as consolidated billing, but you do not place them into any OUs.</u>==??? o i see, it's BECAUSE they do not overlap you DON'T put into OUs but you still take advantage of the benefits of being part of the general organization==

![image-20220518192347870](Module%206%20-%20Security.assets/image-20220518192347870.png)

The HR and legal departments need to access the same AWS services and resources, so you place them into an OU together. <u>Placing them into an OU enables you to attach policies that apply to both the HR and legal departments’ AWS account</u>

### Knowledge Check

**You are configuring service control policies (SCPs) in AWS Organizations. Which identities and resources can SCPs be applied to?** (Select TWO.)

- 

  IAM users

  Incorrectly checked

- 

  IAM groups

  Incorrectly checked

- 

  **An individual member account**

  Correctly checked

- 

  IAM roles

  Incorrectly checked

- 

  **An organizational unit (OU)**

  Correctly checked

SUBMIT

Incorrect

The correct two response options are:

- **An individual member account**
- **An organizational unit (OU)**

In AWS Organizations, you can apply service control policies (SCPs) to the organization root, an individual member account, or an OU. An SCP affects all IAM users, groups, and roles within an account, including the AWS account root user.

 

You can apply IAM policies to IAM users, groups, or roles. You cannot apply an IAM policy to the AWS account root user.

## Compliance

To meet compliance and auditing in AWS

For example, If you run software that runs with consumer data and in Europe, you need to make sure in application you are in complication with GDPR. Or in US when dealing with healh information of individuals, need to make sure in compliance with HIPAA 

==The first thing to note is, AWS has already built out data center infrastructure and networking following industry best practices for security, and as an AWS customer, you inherit all the best practices of AWS policies, architecture, and operational processes.==

- segments of your compliance already there
- <u>Region you operate out of might help you meet compliance</u>, so you can choose a region and AWS won't automatically replicate data across regions. 
- You also should be aware of the fact, <u>you own your data in AWS</u>
  - you own that data and you <u>can employ multiple data encryption mechanisms</u>
- if you need specific standards for data storage, you can do it yourself or use features that already exist
- for a lot of resources, enabling data protection is a configuration on the resource. 
- **AWS also provides a bunch of white papers and documents you can use for compliance reports**
- Since you are not running data yourself, y<u>ou can request, AWS provides you with documentation proving they are following best practices for security and compliance</u>
- ==**AWS artifact**==- allows you to gain access to compliance reports done by third parties who have validated a wide range of compliance standards. 
  - check out **AWS Compliance Center:** will show you compliance enabling services, as well as documentation like AWS Risk and Security White Paper which you should read to make sure you understand
  - 

![image-20220518194656110](Module%206%20-%20Security.assets/image-20220518194656110.png)

### **AWS Artifact**

Depending on your company’s industry, you may need to uphold specific standards. An audit or inspection will ensure that the company has met those standards.

==[**AWS Artifact**](https://aws.amazon.com/artifact) is a service that provides <u>on-demand access to AWS security and compliance reports</u> and <u>select online agreements</u>. AWS Artifact consists of two main sections: **AWS Artifact Agreements** and **AWS Artifact Reports**.==

To learn more, select the **+** symbol next to each section.

==**AWS Artifact Agreements**==

–

Suppose that your company needs to sign an agreement with AWS regarding your use of certain types of information throughout AWS services. You can do this through **AWS Artifact Agreements**. 

 

In AWS Artifact Agreements, y<u>ou can review, accept, and manage agreements for an individual account and for all your accounts in AWS Organizations</u>. D<u>ifferent types of agreements</u> are offered to address the needs of customers who are subject to specific regulations, such as the Health Insurance Portability and Accountability Act (HIPAA).

**==AWS Artifact Reports==**

–

Next, suppose that a member of your company’s development team is building an application and needs more information about their responsibility for complying with certain regulatory standards. You can advise them to access this information in **AWS Artifact Reports**.

 

<u>AWS Artifact Reports provide compliance reports from third-party auditors.</u> These auditors have tested and verified that AWS is compliant with a variety of global, regional, and industry-specific security standards and regulations. AWS Artifact Reports remains up to date with the latest reports released. <u>You can provide the AWS audit artifacts to your auditors or regulators as evidence of AWS security controls.</u> 

The <u>following are some of the compliance reports and regulations</u> that you can find within AWS Artifact. Each report includes a description of its contents and the reporting period for which the document is valid. 

![Icons for some of the compliance reports and regulations that are available in AWS Artifact](Module%206%20-%20Security.assets/MqGHDcunFO8FzCGV_qiguS0QgqBrh0ktF.jpg)

### **Customer Compliance Center**

The [**Customer Compliance Center**](https://aws.amazon.com/compliance/customer-center/) contains resources to help you learn more about AWS compliance. 

In the Customer Compliance Center, you can <u>read customer compliance stories</u> to discover how companies in regulated industries have solved various compliance, governance, and audit challenges.

You can also <u>access compliance whitepapers and documentatio</u>n on topics such as:

- AWS <u>answers to key compliance questions</u>
- An <u>overview of AWS risk and compliance</u>
- An <u>auditing security checklist</u>

Additionally, the Customer Compliance Center includes an <u>auditor learning path</u>. This learning path is designed for individuals in auditing, compliance, and legal roles who want to <u>learn more about how their internal operations can demonstrate compliance using the AWS Cloud</u>.

### Knowledge Check

**<u>Which tasks can you complete in AWS Artifact? (Select TWO.)</u>**

- 

  Access AWS compliance reports on-demand.

  Correctly checked

- 

  Consolidate and manage multiple AWS accounts within a central location.

  Correctly unchecked

- 

  Create users to enable people and applications to interact with AWS services and resources.

  Correctly unchecked

- 

  Set permissions for accounts by configuring service control policies (SCPs).

  Correctly unchecked

- 

  Review, accept, and manage agreements with AWS.

  Correctly checked

SUBMIT

Correct

The correct two response options are:

- **Access AWS compliance reports on-demand.**
- **Review, accept, and manage agreements with AWS.**

The other response options are incorrect because:

- Consolidate and manage multiple AWS accounts within a central location- This task can be completed in *AWS Organizations*.
- Create users to enable people and applications to interact with AWS services and resources- This task can be completed in *AWS Identity and Access Management (IAM)*.
- Set permissions for accounts by configuring service control policies (SCPs)- This task can be completed in *AWS Organizations*.

**Learn more:**

- [AWS Artifact](https://aws.amazon.com/artifact)

---

## **Denial-of-service attacks**

==DDoS== -  Distributed Denial of Service - attack on your enterprise's infrastructure

- AWS can automatically defend your infrastructure

- objective: shut down application by overwhelming it to the point it can not work

  ![image-20220520110350642](Module%206%20-%20Security.assets/image-20220520110350642.png)

  - the attack leverages zombie bots
  - Assault commander do smallest amount of work needed

- ==**UDP Flood**== : based on the national weather service

  - The attacker sends a request but with a fake return address, and your system is forced to deal with responses it never asked for, all designed to assault your network
  - **Solution: Security groups** - only allows proper requested traffic
    - <u>Security groups operate at the AWS Network Level</u> not at the EC2 instance level like an operating system Firewall might 
    - <u>Massive attacks, like UDP Floods and Reflection attacks, get shrugged off by scale of entire AWS Regions capacity</u>
      - this is where size of AWS comes in handy, not that it would be impossible for attackers, but it would be very expensive 

  ![image-20220520110522719](Module%206%20-%20Security.assets/image-20220520110522719.png)

  ![image-20220520110533595](Module%206%20-%20Security.assets/image-20220520110533595.png)

- ==HTTP Level Attacks== - Zombie bots ask for so much returns so customers can't get in. 

  ![image-20220520111108560](Module%206%20-%20Security.assets/image-20220520111108560.png)

  

  - ==**Slowloris attack**== - Instead of normal connection, attacker pretends to have an extremely <u>slow connection.</u> Meanwhile, your production servers are waiting for customer to finish request so they can return result. But can't move on to next thread until gets full packets

    - 'elegantly evil architecture'
    - **Solution: Elastic Load Balancer** - handles HTTP traffic request first and it waits  until entire message (no matter how fast or slow) is complete before sending it over to the front end web server. 
      - you can try to overwhelm it, but since ELB is scalable and it runs at the region level, you'd once again would have to overwhelm the entire AWS Region

    ![image-20220520111053843](Module%206%20-%20Security.assets/image-20220520111053843.png)

    - ![image-20220520111908392](Module%206%20-%20Security.assets/image-20220520111908392.png)

  - For the sharpest most sophisticated attacks, AWS offers specialized defense tool called ==**AWS Shield  with AWS WAF**==

    - ![image-20220520112007018](Module%206%20-%20Security.assets/image-20220520112007018.png)
    - **AWS WAF uses a web application firewall to filter incoming traffic for signatures of bad actors.** It has extensive machine learning capabilities and can recognize new threats as they evolve, and proactively help defend  your system against an evergrowing list of destructive vectors

==The takeaway is a well-architected system is already defended against most attacks. And by using **AWS Shield Advanced**, you can turn AWS into your partner against DDoS attacks.==



Customers can call the coffee shop to place their orders. After answering each call, a cashier takes the order and gives it to the barista. 

However, suppose that a prankster is calling in multiple times to place orders but is never picking up their drinks. This causes the cashier to be unavailable to take other customers’ calls. The coffee shop can attempt to stop the false requests by blocking the phone number that the prankster is using. 

In this scenario, the prankster’s actions are similar to a **denial-of-service attack**.

### **Denial-of-service attacks**

==A **denial-of-service (DoS) attack** is a deliberate attempt to make a website or application unavailable to users.==

![Illustration of a denial-of-service attack, in which the attack originates from a single source](Module%206%20-%20Security.assets/Wcb6GrGI_Gb51NR6_zHLWu4-HXE9BERnI.png)

For example, an attacker might <u>flood a website or application with excessive network traffic</u> until the targeted website or application becomes overloaded and is no longer able to respond. If the <u>website or application becomes unavailable, this denies service to users who are trying to make legitimate requests.</u>

### **Distributed denial-of-service attacks**

Now, suppose that the prankster has enlisted the help of friends. 

The prankster and their friends repeatedly call the coffee shop with requests to place orders, even though they do not intend to pick them up. These requests are coming in from different phone numbers, and it’s impossible for the coffee shop to block them all. Additionally, the influx of calls has made it increasingly difficult for customers to be able to get their calls through. This is similar to a **distributed denial-of-service attack**.

![Illustration of a distributed denial-of-service attack, in which the attack originates from multiple sources](Module%206%20-%20Security.assets/FE0B4YmzsY1tXwRd_y9LA-qvCGRPP_4HE.png)

==In a distributed denial-of-service (DDoS) attack, multiple sources are used to start an attack that aims to make a website or application unavailable.==This can come from a group of attackers, or even a single attacker. The single attacker <u>can use multiple infected computers</u> (also known as “bots”) to send excessive traffic to a website or application.

==To help minimize the effect of DoS and DDoS attacks on your applications, you can use [**AWS Shield**](https://aws.amazon.com/shield).==

### **AWS Shield**

AWS Shield is a service that protects applications against DDoS attacks. AWS Shield provides two levels of protection: Standard and Advanced.

To learn more, select the **+** symbol next to each service.

AWS Shield Standard

–

==**AWS Shield Standard** automatically protects all AWS customers at no cost. It protects your AWS resources from the most common, frequently occurring types of DDoS attacks.==

As network traffic comes into your applications, AWS Shield Standard uses a variety of <u>analysis techniques to detect malicious traffic in real time and automatically mitigates it</u>. 

AWS Shield Advanced

–

==**AWS Shield Advanced** is a paid service that <u>provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks.</u>==



It also integrates with other services such as Amazon CloudFront, Amazon Route 53, and Elastic Load Balancing. Additionally, <u>you can integrate AWS Shield with AWS WAF by writing custom rules to mitigate complex DDoS attacks</u>.

## Additional Security Services

==Encryption== - <u>securing a message or data in a way that only authorized parties can access it</u>

1. **encryption at rest** 

![image-20220520123531667](Module%206%20-%20Security.assets/image-20220520123531667.png)

2. **encryption in transit**

   ![image-20220520123618000](Module%206%20-%20Security.assets/image-20220520123618000.png)

   or another aWS service

   ![image-20220520123630788](Module%206%20-%20Security.assets/image-20220520123630788.png)

   - can use SSL and server certificates to validate and authorize a client
     This means data is protected when passing between them. 
   - SQS. S3. RDS, etc.

![image-20220520123803687](Module%206%20-%20Security.assets/image-20220520123803687.png)

==**Amazon Inspector** - helps to improve security and compliance of AWS deployed applications by running an automated security assessment against your infrastructure==

- specifically it helps to check for deviations on your security best practices: like exposure of EC2 instances, vulnerabilities and so on 
- Consists of 3 parts: 
  1. **Network configuration reachability** piece
  2. **Amazon agent** - which can be installed on EC2 instances
  3. **Security assessment service** - that brings them all together

- To use it:  <u>you configure Inspector options, run the service, out pops a list of potential security issues. The resulting findings are displayed in the Amazon Inspector console, and they are presented with a detailed description of the security issue, and a recommendation on how to fix it.</u> 

  ![image-20220520124421251](Module%206%20-%20Security.assets/image-20220520124421251.png)

  ![image-20220520124352817](Module%206%20-%20Security.assets/image-20220520124352817.png)

  ![Screen Shot 2022-05-20 at 12.45.18 PM](Module%206%20-%20Security.assets/Screen%20Shot%202022-05-20%20at%2012.45.18%20PM.png)

  ![Screen Shot 2022-05-20 at 12.45.23 PM](Module%206%20-%20Security.assets/Screen%20Shot%202022-05-20%20at%2012.45.23%20PM.png)

  ![Screen Shot 2022-05-20 at 12.45.27 PM](Module%206%20-%20Security.assets/Screen%20Shot%202022-05-20%20at%2012.45.27%20PM.png)

  ![Screen Shot 2022-05-20 at 12.45.31 PM](Module%206%20-%20Security.assets/Screen%20Shot%202022-05-20%20at%2012.45.31%20PM.png)

- Additionally, you can retrieve findings through an API to go towards best practice of performing remediation to fix issues

- Another service is ==**Amazon GuardDuty** - analyzes continuous stream data generated from your account and network activity==

  - found on Amazon Cloudtrail events, Amazon VPC Flow logs, and DNS logs
  - It uses integrated threat intelligence - such as known malicious IP addresses, anomaly detection, and machine learning to identify threats more accurately,
    - runs independently of your AWS services, so it won't affect availability or performance of your existing infrastructure and workloads
    - So many other security services like Advanced Shield and Security Hub

- ![image-20220520125110643](Module%206%20-%20Security.assets/image-20220520125110643.png)

### **AWS Key Management Service (AWS KMS)**

The coffee shop has many items, such as coffee machines, pastries, money in the cash registers, and so on. You can think of these items as data. The coffee shop owners want to ensure that all of these items are secure, whether they’re sitting in the storage room or being transported between shop locations. 

In the same way, you must ensure that your applications’ data is secure while in storage **(encryption at rest)** and while it is transmitted, known as **encryption in transit**.

==[**AWS Key Management Service (AWS KMS)**](https://aws.amazon.com/kms) enables you to perform encryption operations through the use of **cryptographic keys**.== <u>A cryptographic key is a random string of digits used for locking (encrypting) and unlocking (decrypting) data</u>. You can use A<u>WS KMS to create, manage, and use cryptographic keys</u>. You can also control the use of keys across a wide range of services and in your applications.

With AWS KMS, <u>you can choose the specific levels of access contro</u>l that you need for your keys. For example, <u>you can specify which IAM users and roles are able to manage keys</u>. Alternatively, <u>you can temporarily disable keys</u> so that they are no longer in use by anyone. <u>Your keys never leave AWS KMS</u>, and you are always in control of them.

### **AWS WAF**

==[**AWS WAF**](https://aws.amazon.com/waf) is a web application firewall that lets you monitor network requests that come into your web applications.==

AWS WAF <u>works together with Amazon CloudFront and an Application Load Balancer</u>. Recall the network access control lists that you learned about in an earlier module. AWS WAF works in a similar way to block or allow traffic. However, <u>it does this by using a [**web access control list (ACL)**](https://docs.aws.amazon.com/waf/latest/developerguide/web-acl.html) to protect your AWS resources</u>. 

Here’s an example of how you can use AWS WAF to allow and block specific requests.

![Illustration of AWS WAF allowing a packet request from a customer](Module%206%20-%20Security.assets/P0njihINh87NtsIv_i_ycrK8iLOIQNINV.png)

Suppose that your application has been receiving malicious network requests from several IP addresses. You want to prevent these requests from continuing to access your application, but you also want to ensure that legitimate users can still access it. You configure the web ACL to allow all requests except those from the IP addresses that you have specified.

When a request comes into AWS WAF, it checks against the list of rules that you have configured in the web ACL. If a request did not come from one of the blocked IP addresses, it allows access to the application.

![Illustration of AWS WAF denying a malicious packet request from a hacker](Module%206%20-%20Security.assets/I79Hxnt_6QcPXQu__pyp_mmWA2_PTZU7t.png)

However, <u>if a request came from one of the blocked IP addresses that you have specified in the web ACL, it is denied access</u>.

### **Amazon Inspector**

Suppose that the developers at the coffee shop are developing and testing a new ordering application. They want to make sure that they are designing the application in accordance with security best practices. However, they have several other applications to develop, so they cannot spend much time conducting manual assessments. To perform automated security assessments, they decide to use [**Amazon Inspector**](https://aws.amazon.com/inspector/).

<u>Amazon Inspector helps to improve the security and compliance of applications by running automated security assessments.</u> It <u>checks applications for security vulnerabilities and deviations from security best practices</u>, such as open access to Amazon EC2 instances and installations of vulnerable software versions. 

After Amazon Inspector has performed an assessment, it <u>provides you with a list of security finding</u>s. The list prioritizes by <u>severity level, including a detailed description of each security issue and a recommendation for how to fix it.</u> However, AWS does not guarantee that following the provided recommendations resolves every potential security issue. Under the <u>shared responsibility model, customers are responsible for the security of their applications, processes, and tools that run on AWS services</u>.

### **Amazon GuardDuty**

==[**Amazon GuardDuty**](https://aws.amazon.com/guardduty) is a service that provides intelligent threat detection for your AWS infrastructure and resources.== It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment.

![Process diagram of the steps for using Amazon GuardDuty](Module%206%20-%20Security.assets/SCqo1b56-Fa_6DRt_phaFiuF9QHWbEoD0.png)

<u>After you have enabled GuardDuty for your AWS account, GuardDuty begins monitoring your network and account activity</u>. You <u>do not have to deploy or manage any additional security software</u>. GuardDuty then continuously analyzes data from <u>multiple AWS sources, including VPC Flow Logs and DNS logs</u>. 

If GuardDuty detects any threats, you can review detailed findings about them from the AWS Management Console. Findings include recommended steps for remediation. <u>You can also configure AWS Lambda functions to take remediation steps automatically in response to GuardDuty’s security findings</u>.

## Summary

In Module 6, you learned about the following concepts:

- **The <u>shared responsibility model</u>**

- **Features of <u>AWS Identity and Access Management</u>**

  - users, groups, roles, policies
  - identity federation - you can federate users to role based account, map ot corporate
  - enable MFA

- **Methods of managing multiple accounts in AWS Organizations**

  - in a hiearchical fashion

- **AWS compliance resources**

  -  AWS Compliance Center, AWS Artifacts

- **AWS services for application security and encryption**

  - ELB, Security Groups, AWS Shield and AWS WAF
  - encryption in transit and at rest
  - Least Privileged Principle
  - Encrypt at every layer

  ==Top priority of AWS is security==

## **Additional resources**

To learn more about the concepts that were explored in Module 6, review these resources.

- [Security, Identity, and Compliance on AWS](https://aws.amazon.com/products/security)
- [Whitepaper: Introduction to AWS Security](https://docs.aws.amazon.com/whitepapers/latest/introduction-aws-security/welcome.html)
- [Whitepaper: Amazon Web Services - Overview of Security Processes](https://docs.aws.amazon.com/whitepapers/latest/aws-overview-security-processes/aws-overview-security-processes.pdf)
- [AWS Security Blog](https://aws.amazon.com/blogs/security/)
- [AWS Compliance](https://aws.amazon.com/compliance)
- [AWS Customer Stories: Security, Identity, and Compliance](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc|product%23api-gateway|product%23cloudfront|product%23route53|product%23directconnect|product%23elb&awsf.customer-references-category=category%23security-identity-compliance)



### Module 6 Quiz

---

**Which statement best describes an IAM policy?**

The correct response option is: **A document that grants or denies permissions to AWS services and resource**s.

 

<u>IAM policies provide you with the flexibility to customize users’ levels of access to resources</u>. For instance, you can allow users to access all the Amazon S3 buckets in your AWS account or only a specific bucket.



The other response options are incorrect because:

- Multi-factor authentication (MFA) is an authentication process that provides an extra layer of protection for your AWS account.
- An IAM role is an identity that you can assume to gain temporary access to permissions.
- The root user identity is the identity that is established when you first create an AWS account.

**Learn more:**

- [AWS IAM: Policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

---

**<u>An employee requires temporary access to create several Amazon S3 buckets. Which option would be the best choice for this task?</u>**

The correct answer is **IAM role**.

 

<u>An IAM role is an identity that you can assume to gain temporary access to permissions.</u> When someone assumes an IAM role, they abandon all permissions that they had under a previous role and assume the permissions of the new role. IAM roles are ideal for situations in which access to services or resources needs to be granted temporarily instead of long-term.

The other response options are incorrect because:

- The AWS account root user is established when you first create an AWS account. As a best practice, do not use the root user for everyday tasks.
- Although you can attach IAM policies to an IAM group, this would not be the best choice for this scenario because the employee only needs to be granted temporary permissions.
- Service control policies (SCPs) enable you to centrally control permissions for the accounts in your organization. An SCP is not the best choice for granting temporary permissions to an individual employee.

**Learn more:**

- [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)

---

**<u>Which statement best describes the principle of least privilege?</u>**

The correct response option is: **Granting only the permissions that are needed to perform specific job tasks.**

 

When you grant permissions by following the <u>principle of least privilege, you prevent users or roles from having more permissions than needed to perform specific job task</u>s. For example, cashiers in the coffee shop should be given access to the cash register system. <u>As a best practice, grant IAM users and roles a minimum set of permissions and then grant additional permissions as needed.</u>



**Learn more:**

- [Security best practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

---

**<u>Which service helps protect your applications against distributed denial-of-service (DDoS) attacks?</u>**

The correct response option is **AWS Shield.**



As network traffic comes into your applications, <u>AWS Shield uses a variety of analysis techniques to detect potential DDoS attacks in real time and automatically mitigates them.</u>



The other response options are incorrect because:

- <u>Amazon GuardDuty is a service that provides intelligent threat detection for your AWS infrastructure and resources</u>. It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment.
- <u>Amazon Inspector</u> checks applications for security vulnerabilities and deviations from security best practices, such as open access to Amazon EC2 instances and installations of vulnerable software versions.
- <u>AWS Artifact is a service that provides on-demand access to AWS security and compliance reports</u> and select online agreements.

**Learn more:**

- [AWS Shield](https://aws.amazon.com/shield/)

---

**<u>Which task can AWS Key Management Service (AWS KMS) perform?</u>**

The correct response option is: **Create cryptographic keys**.

 

<u>AWS Key Management Service (AWS KMS) enables you to perform encryption operations through the use of cryptographic keys.</u> A cryptographic key is a random string of digits used for locking (encrypting) and unlocking (decrypting) data. You can use AWS KMS to create, manage, and use cryptographic keys. You can also control the use of keys across a wide range of services and in your applications.

 

The other response options are incorrect because:

- You can configure multi-factor authentication (MFA) in *AWS Identity and Access Management (IAM)*.
- You can update the AWS account root user password in *the AWS Management Console.*
- You can assign permissions to users and groups in *AWS Identity and Access Management (IAM)*.