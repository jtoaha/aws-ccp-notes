6/26/22

udemy practice exam

==AWS Lambda Pricing==

- number of requests
- *GB*-*seconds* are the number of seconds your function runs for, multiplied by the amount of RAM memory consumed. 

==VPC Site-to-Site==



By default, instances that you launch into an Amazon VPC can't communicate with your own (remote)        network. You can <u>enable access to your remote network from your VPC</u> by creating an AWS Site-to-Site VPN        (Site-to-Site VPN) connection, and configuring routing to pass traffic through the connection.

An ==Amazon Machine Image (AMI)== is a supported and maintained image provided by AWS that 	provides the information required to launch an instance. You must specify an AMI when you 	launch an instance. You can launch multiple instances from a single AMI when you require 	multiple instances with the same configuration. You can use different AMIs to launch 	instances when you require instances with different configurations.

==Route 53 configuration policies==

When you create a record, you choose a routing policy, which determines how Amazon Route 53 responds to queries: 

- **Simple routing policy** – Use for a single resource that 				performs a given function for your domain, for example, a web server that serves 				content for the example.com website. You can use simple routing to create 				records in a private hosted zone.
- **Failover routing policy** – Use when you want to 				configure active-passive failover.  You can use failover routing to create 				records in a private hosted zone.
- **Geolocation routing policy** – Use when you want to 				route traffic based on the location of your users.  You can use geolocation 				routing to create records in a private hosted zone.
- **Geoproximity routing policy** – Use when you want to route traffic  			based on the location of your resources and, optionally, shift traffic from resources in one location  			to resources in another.
- **Latency routing policy** – Use when you have resources 				in multiple AWS Regions and you want to route traffic to the region that 				provides the best latency.  You can use latency routing to create records in a 				private hosted zone.
- **IP-based routing policy** – Use when you want to route 				traffic based on the location of your users, and have the IP addresses that the 				traffic originates from.
- **Multivalue answer routing policy** – Use when you want 				Route 53 to respond to DNS queries with up to eight healthy records selected at 				random.  You can use multivalue answer routing to create records in a private 				hosted zone.
- **Weighted routing policy** – Use to route traff

---

#### Explanation

Correct options:

==Most of the services that AWS offers are Region specific.== But few  services, by definition, need to be in a global scope because of the  underlying service they offer. AWS IAM, Amazon CloudFront, Route 53 and  WAF are some of the global services.

**AWS Lambda** - AWS Lambda is a compute service that  lets you run code without provisioning or managing servers. AWS Lambda  executes your code only when needed and scales automatically, from a few requests per day to thousands per second. Lambda is a regional service.

**Amazon Rekognition** - With Amazon Rekognition, you  can identify objects, people, text, scenes, and activities in images and videos, as well as detect any inappropriate content. Amazon Rekognition also provides highly accurate facial analysis and facial search  capabilities that you can use to detect, analyze, and compare faces for a wide variety of user verification, people counting, and public safety  use cases. Rekognition is a regional service.

Incorrect options:

**AWS Identity and Access Management (IAM)** - AWS  Identity and Access Management (IAM) enables you to manage access to AWS services and resources securely. Using IAM, you can create and manage  AWS users and groups, and use permissions to allow and deny their access to AWS resources.

**Amazon CloudFront** - Amazon CloudFront is a fast  content delivery network (CDN) service that securely delivers data,  videos, applications, and APIs to customers globally with low latency,  high transfer speeds, all within a developer-friendly environment.

**AWS WAF** - By using AWS WAF, you can configure web  access control lists (Web ACLs) on your CloudFront distributions or  Application Load Balancers to filter and block requests based on request signatures.

As mentioned earlier, these three services are global in scope.

Exam Alert:

**Amazon S3** - Amazon S3 is a unique service in the  sense that it follows a global namespace but the buckets are regional.  You specify an AWS Region when you create your Amazon S3 bucket. This is a regional service.

---

#### Explanation

Correct options:

Most of the services that AWS offers are Region specific. But few  services, by definition, need to be in a global scope because of the  underlying service they offer. AWS IAM, Amazon CloudFront, Route 53 and  WAF are some of the global services.

**AWS Lambda** - AWS Lambda is a compute service that  lets you run code without provisioning or managing servers. AWS Lambda  executes your code only when needed and scales automatically, from a few requests per day to thousands per second. Lambda is a regional service.

**Amazon Rekognition** - With Amazon Rekognition, you  can identify objects, people, text, scenes, and activities in images and videos, as well as detect any inappropriate content. Amazon Rekognition also provides highly accurate facial analysis and facial search  capabilities that you can use to detect, analyze, and compare faces for a wide variety of user verification, people counting, and public safety  use cases. Rekognition is a regional service.

Incorrect options:

**AWS Identity and Access Management (IAM)** - AWS  Identity and Access Management (IAM) enables you to manage access to AWS services and resources securely. Using IAM, you can create and manage  AWS users and groups, and use permissions to allow and deny their access to AWS resources.

**Amazon CloudFront** - Amazon CloudFront is a fast  content delivery network (CDN) service that securely delivers data,  videos, applications, and APIs to customers globally with low latency,  high transfer speeds, all within a developer-friendly environment.

**AWS WAF** - By using AWS WAF, you can configure web  access control lists (Web ACLs) on your CloudFront distributions or  Application Load Balancers to filter and block requests based on request signatures.

As mentioned earlier, these three services are global in scope.

Exam Alert:

**Amazon S3** - Amazon S3 is a unique service in the  sense that it follows a global namespace but the buckets are regional.  You specify an AWS Region when you create your Amazon S3 bucket. This is a regional service.

---

**DynamoDB** - Amazon DynamoDB is a key-value and  document database that delivers single-digit millisecond performance at  any scale. It's a f<u>ully managed, multi-Region, multi-master, durable  database with built-in security, backup and restore, and in-memory  caching for internet-scale applications</u>. All of your data is stored on  solid-state disks (SSDs) and is automatically replicated across multiple Availability Zones in an AWS Region, providing built-in high  availability and data durability.

DynamoDB High Availability: ![img](062622%20-%20AWS%20Practice%20Questions.assets/pt3-q12-i1.jpg) via - https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html

**EFS** - Amazon Elastic File System (Amazon EFS)  provides a simple, scalable, fully managed elastic NFS file system for  use with AWS Cloud services and on-premises resources. It is built to  scale on-demand to petabytes without disrupting applications, growing  and shrinking automatically as you add and remove files, eliminating the need to provision and manage capacity to accommodate growth. Amazon EFS is a regional service storing data within and across multiple  Availability Zones (AZs) for high availability and durability.

EFS High Availability: ![img](062622%20-%20AWS%20Practice%20Questions.assets/pt3-q12-i2.jpg) via - https://aws.amazon.com/efs/faq/

Incorrect options:

**Redshift** - Amazon Redshift is a fast, fully managed  cloud data warehouse that makes it simple and cost-effective to analyze  all your data using standard SQL and your existing Business Intelligence (BI) tools.

Amazon Redshift only supports Single-AZ deployments: ![img](062622%20-%20AWS%20Practice%20Questions.assets/pt3-q12-i3.jpg) via - https://aws.amazon.com/redshift/faqs/

**EBS** - Amazon Elastic Block Store (EBS) is an easy to use, high-performance block storage service designed for use with  Amazon Elastic Compute Cloud (EC2) for both throughput and  transaction-intensive workloads at any scale. EBS volumes are replicated within an Availability Zone (AZ) and can easily scale to petabytes of  data.

**Instance Store** - As Instance Store volumes are tied to an EC2 instance, they are also single AZ entities.

---

AWS Identity and Access Management (IAM) policies are written as JSON  documents. Which of the following are mandatory elements of an IAM  policy?

**Effect, Action** - Most policies are stored in AWS as  JSON documents. Identity-based policies and policies used to set  permissions boundaries are JSON policy documents that you attach to a  user or role. Resource-based policies are JSON policy documents that you attach to a resource.

A JSON policy document includes these elements:

1. Optional policy-wide information at the top of the document
2. One or more individual statements

Each statement includes information about a single permission. The  information in a statement is contained within a series of elements.

1. Version – Specify the version of the policy language that you  want to use. As a best practice, use the latest 2012-10-17 version.
2. Statement – Use this main policy element as a container for the  following elements. You can include more than one statement in a policy.
   1. Sid (Optional) – Include an optional statement ID to differentiate between your statements.
   2. Effect – Use Allow or Deny to indicate whether the policy allows or denies access.
   3. Principal (Required in only some circumstances) – If you create a resource-based policy, you must indicate the account, user, role, or  federated user to which you would like to allow or deny access. If you  are creating an IAM permissions policy to attach to a user or role, you  cannot include this element. The principal is implied as that user or  role.
   4. Action – Include a list of actions that the policy allows or denies.
   5. Resource (Required in only some circumstances) – If you create an IAM permissions policy, you must specify a list of resources to which  the actions apply. If you create a resource-based policy, this element  is optional. If you do not include this element, then the resource to  which the action applies is the resource to which the policy is  attached.
   6. Condition (Optional) – Specify the circumstances under which the policy grants permission.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "FirstStatement", # optional
      "Effect": "Allow", # required - indicate whether the policy allows or denies access.
      "Action": ["iam:ChangePassword"], # required - Include a list of actions that the policy allows or denies.
      "Resource": "*"  # optional -  If you create an IAM permissions policy, you must specify a list of resources to which  the actions apply.
    },
    {
      "Sid": "SecondStatement",
      "Effect": "Allow",
      "Action": "s3:ListAllMyBuckets",
      "Resource": "*"
    },
    {
      "Sid": "ThirdStatement",
      "Effect": "Allow",
      "Action": [
        "s3:List*",
        "s3:Get*"
      ],
      "Resource": [
        "arn:aws:s3:::confidential-data",
        "arn:aws:s3:::confidential-data/*"
      ],
      "Condition": {"Bool": {"aws:MultiFactorAuthPresent": "true"}}
    }
  ]
}
```

----

Which of the following capabilities does Amazon Rekognition provide as a ready-to-use feature?

#### Explanation

Correct option:

**Identify objects in a photo**

With Amazon Rekognition, you can identify objects, people, text,  scenes, and activities in images and videos, as well as detect any  inappropriate content. Amazon Rekognition also provides highly accurate  facial analysis and facial search capabilities that you can use to  detect, analyze, and compare faces for a wide variety of user  verification, people counting, and public safety use cases.

Amazon Rekognition Use-Cases:

![img](062622%20-%20AWS%20Practice%20Questions.assets/pt3-q10-i1.jpg) via - https://aws.amazon.com/rekognition/

![img](062622%20-%20AWS%20Practice%20Questions.assets/pt3-q10-i2.jpg) via - https://aws.amazon.com/rekognition/

Incorrect options:

**Convert images into greyscale**

**Resize images quickly**

**Human pose detection**

Amazon Rekognition does not do image processing tasks such as  converting images to greyscale or resizing images. Human pose detection  is not available in Amazon Rekognition.

Reference:

---

**Use CloudWatch Logs for both the EC2 instance and the on-premises servers**

You can use Amazon CloudWatch Logs to monitor, store, and access your log files from Amazon Elastic Compute Cloud (Amazon EC2) instances, AWS CloudTrail, Route 53, and other sources such as on-premises servers.

==CloudWatch Logs enables you to centralize the logs from all of your  systems, applications, and AWS services that you use, in a single,  highly scalable service.== You can then easily view them, search them for  specific error codes or patterns, filter them based on specific fields,  or archive them securely for future analysis.

==AWS CloudTrail is a service that enables governance, compliance,  operational auditing, and risk auditing of your <u>AWS account</u>.== With  CloudTrail, you can log, continuously monitor, and retain account  activity related to actions across your AWS infrastructure. CloudTrail  provides event history of your AWS account activity, including actions  taken through the AWS Management Console, AWS SDKs, command-line tools,  and other AWS services. CloudTrail cannot be used to centralize the  server logs for EC2 instances or on-premises servers,

---

"Create separate AWS accounts for development and production environments to receive separate invoices"

==Every AWS account provides its own invoice end of the month.=== You can  get separate invoices for development and production environments by  setting up separate AWS accounts for each environment.

---

Which of the following AWS entities provides the information required to launch an EC2 instance?

**AMI**

An Amazon Machine Image (AMI) provides the information required to  launch an instance. You must specify an AMI when you launch an instance.

An AMI includes the following:

One or more EBS snapshots, or, for instance-store-backed AMIs, a  template for the root volume of the instance (for example, an operating  system, an application server, and applications).

Launch permissions that control which AWS accounts can use the AMI to launch instances.

A block device mapping that specifies the volumes to attach to the instance when it's launched.

The following diagram summarizes the AMI lifecycle: ![img](062622%20-%20AWS%20Practice%20Questions.assets/ami_lifecycle.png)

----

An organization maintains separate VPCs for each of its departments.  With expanding business, the organization now wants to connect all VPCs  for better departmental collaboration. Which AWS service will help the  organization tackle the issue effectively?

#### Explanation

Correct option:

**AWS Transit Gateway**

==AWS Transit Gateway connects VPCs and on-premises networks through a  central hub.== This simplifies your network and puts an end to complex  peering relationships. It acts as a cloud router – each new connection  is only made once. As you expand globally, inter-Region peering connects AWS Transit Gateways using the AWS global network. <u>Your data is  automatically encrypted and never travels over the public internet.</u>

How Transit Gateway can simplify your network: ![img](062622%20-%20AWS%20Practice%20Questions.assets/pt3-q5-i1.jpg) via - https://aws.amazon.com/transit-gateway/

Incorrect options:

==**VPC Peering** - A VPC peering connection is a  networking connection between <u>two VPCs</u> that enables you to route traffic between them privately.== VPC peering is not transitive, a separate VPC  peering connection has to be made between two VPCs that need to talk to  each other. With growing VPCs, this gets difficult to manage.

Transitive VPC Peering is not allowed: ![img](062622%20-%20AWS%20Practice%20Questions.assets/transitive-peering-diagram.png) via - https://docs.aws.amazon.com/vpc/latest/peering/invalid-peering-configurations.html

**AWS Direct Connect** - AWS Direct Connect creates a  dedicated private connection from a remote network to your VPC. This is a private connection and does not use the public internet. Takes at least a month to establish this connection. Direct Connect cannot be used to  interconnect VPCs.

**Site to Site VPN** - AWS Site-to-Site VPN creates a  secure connection between your data center or branch office and your AWS cloud resources. <u>This connection goes over the public internet.</u> Site to Site VPN cannot be used to interconnect VPCs.

Reference:

https://aws.amazon.com/transit-gateway/

---

Which of the following is correct regarding the AWS Shield Advanced pricing?

#### Explanation

Correct option:

**AWS Shield Advanced offers protection against higher fees that could result from a DDoS attack**

==AWS Shield Advanced offers some cost protection against spikes in  your AWS bill that could result from a DDoS attack.== This cost protection is provided for your Elastic Load Balancing load balancers, Amazon  CloudFront distributions, Amazon Route 53 hosted zones, Amazon Elastic  Compute Cloud instances, and your AWS Global Accelerator accelerators.

==AWS Shield Advanced is a paid service for all customers, irrespective of the Support plan.==

Incorrect options:

**AWS Shield Advanced is a free service for AWS Enterprise Support plan**

**AWS Shield Advanced is a free service for AWS Business Support plan**

**AWS Shield Advanced is a free service for all AWS Support plans**

These three options contradict the details provided earlier in the explanation, so these options are incorrect.

Reference:

---

What is the primary benefit of deploying an RDS database in a Read Replica configuration?

**Read Replica improves database scalability**

Amazon Relational Database Service (Amazon RDS) makes it easy to set  up, operate, and scale a relational database in the cloud. Read Replicas allow you to <u>create read-only copies that are synchronized with your  master database</u>. Read Replicas are used for improved read performance.  You can also place your read replica in a <u>different AWS Region closer to your users</u> for better performance. Read Replicas are an example of  <u>horizontal scaling</u> of resources.

Read Replica Overview: ![img](062622%20-%20AWS%20Practice%20Questions.assets/pt3-q31-i1.jpg) via - https://aws.amazon.com/rds/features/multi-az/

Exam Alert:

Please review the differences between Multi-AZ, Multi-Region and Read Replica deployments for RDS: ![img](062622%20-%20AWS%20Practice%20Questions.assets/pt3-q31-i2.jpg) via - https://aws.amazon.com/rds/features/multi-az/

Incorrect options:

**Read Replica enhances database availability** -==Amazon  RDS Multi-AZ deployments provide enhanced availability and durability  for RDS database (DB) instances==, making them a natural fit for  production database workloads. When you provision a Multi-AZ DB  Instance, Amazon RDS automatically creates a primary DB Instance and  synchronously replicates the data to a standby instance in a different  Availability Zone (AZ). Read Replica cannot enhance database  availability.

**Read Replica protects the database from a regional failure** - You need to use RDS in Multi-Region deployment configuration to  protect from a regional failure. Read Replica cannot protect from a  regional failure.

**Read Replica reduces database usage costs** - RDS with Read Replicas increases the database costs compared to the standard deployment. So this option is incorrect.

Reference:

A system is said to be scalable if it can increase its workload and  throughput when additional resources are added. A related aspect of  scalability is availability and **the ability of the system to undergo administration and servicing without impacting applications and end user accessibility**.

---

A cyber-security agency uses AWS Cloud and wants to carry out security  assessments on their own AWS infrastructure without any prior approval  from AWS. Which of the following describes/facilitates this practice?

#### Explanation

Correct option:

**Penetration Testing**

AWS customers can carry out security assessments or penetration tests against their AWS infrastructure without prior approval for few common  AWS services. Customers are not permitted to conduct any security  assessments of AWS infrastructure, or the AWS services themselves.

Incorrect options:

**Network Stress Testing** - AWS considers "network  stress test" to be when a test sends a large volume of legitimate or  test traffic to a specific intended target application. The endpoint and infrastructure are expected to be able to handle this traffic.

**Amazon Inspector** - Amazon Inspector is an automated, security assessment service that helps you check for unintended network accessibility of your Amazon EC2 instances and for vulnerabilities on  those EC2 instances. Amazon Inspector assessments are offered to you as  pre-defined rules packages mapped to common security best practices and  vulnerability definitions.

**AWS Secrets Manager** - AWS Secrets Manager helps you  protect secrets needed to access your applications, services, and IT  resources. The service enables you to easily rotate, manage, and  retrieve database credentials, API keys, and other secrets throughout  their lifecycle. Users and applications retrieve secrets with a call to  Secrets Manager APIs, eliminating the need to hardcode sensitive  information in plain text.

---

==Cost Allocation Tags==

**For each resource, each tag key must be unique, and each tag key can have only one value**

**You must activate both AWS generated tags and user-defined  tags separately before they can appear in Cost Explorer or on a cost  allocation report**

A Cost Allocation Tag is a label that you or AWS assigns to an AWS  resource. Each tag consists of a key and a value. For each resource,  each tag key must be unique, and each tag key can have only one value.  You can use tags to organize your resources, and cost allocation tags to track your AWS costs on a detailed level.

AWS provides two types of cost allocation tags, an AWS generated tags and user-defined tags. AWS defines, creates, and applies the AWS  generated tags for you, and you define, create, and apply user-defined  tags. You must activate both types of tags separately before they can  appear in Cost Explorer or on a cost allocation report.

AWS Cost Allocation Tags Overview: ![img](062622%20-%20AWS%20Practice%20Questions.assets/pt3-q64-i1.jpg) via - https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html

Incorrect options:

---

S3 One Zone-IA is for data that is accessed less frequently but  requires rapid access when needed. Unlike other S3 Storage Classes which store data in a minimum of three Availability Zones (AZs), S3 One  Zone-IA stores data in a single AZ.

Please review this illustration for S3 Storage Classes availability.  You don't need to memorize the actual numbers, just remember that S3 One Zone-IA offers the lowest availability:

----

7/1/22

Practice Test # 4 First Attempt: 49%!!!! My grades keep getting lower from %72 -> %70 -> %60 

amazon light sail - virtual servers for managing containers, instances, databases



- [ ] Device Farm
- [ ] Mobile Farm
- [ ] AWS services offer LifeCycle Management 
- [ ] Step Function
- [ ] AWS Storage Gateway
- [ ] Disaster Recovery
  - [ ] Backup and Restore strategy
  - [ ] Pilot Light strategy
  - [ ] Warm Standby strategy
  - [ ] Multi-site active-active strategy
- [ ] Global accelerator vs CloudFront
- [ ] AWS routing policies
  - [ ] Failover
  - [ ] Simple
  - [ ] Latency
  - [ ] Weighted

 Bob receives the cost-benefit from Susan's Reserved Instances only if  he launches his instances in the same Availability Zone where Susan  purchased her Reserved Instances.

==AWS Marketplace== offers sellers 2 ways to deliver software: 1) AMI Image 2) Software as a Service

- AMI is preferred option

---

**On-Demand instance** - you have full control over lifecycle

**Reserved Instances** - does not refer to physical instances - rather it is a billing discount applied to the use of On-Demand instances in your account

**Dedicated Host** - physical server fully dedicated for your use

---

 Amazon S3 infrastructure is managed by AWS. So, Reserved Instance does  not make sense here. But, S3 offers volume discounts for its storage  classes.

----



AWS Trusted Advice provides real time guidance on provisioning resources according to best practices

AWS Trusted Advisor is an online tool that provides real-time guidance  to help provision your resources following AWS best practices.

- Cost Optimization, Performance, Security, Fault Tolerance, Service Limits.

==Trusted Advisor inspects your AWS environment and makes recommendations  when opportunities may exist to save money, improve system performance, or close security gaps.== It provides  alerts on several of the most common security misconfigurations that can occur, including leaving certain ports open that make you vulnerable to hacking and unauthorized access, neglecting to create IAM accounts for  your internal users, allowing public access to Amazon S3 buckets, not  turning on user activity logging (AWS CloudTrail), or not using MFA on  your root AWS Account.

---

You can generate and download a ==credential report== that lists all users  in your account and the status of their various credentials, including  passwords, access keys, and MFA devices. Y

AWS Systems Manager gives you visibility and control of your infrastructure on AWS. 

==AWS Fargate is a purpose-built serverless compute engine for containers.==

UP to question 18 - make sure to read and and retake the exam

**AWS Cloud Formation** - modeling and provisioning AWS and 3rd party resources`	

**AWS CodeDeploy** - automations deployment to AWS resources, such EC2, Fargate, Lambda, and on-premise instances

**Credentials reports** -  lists all users in your account and the status of their various account aspects such as passwords, access keys, and MFA devices

System Mangers- centrally manage services on AWS Cloud and on-premise data center



**AWS Trusted Advisor** - helps provision your resources following AWS best practices. AWS service can help you analyze your infrastructure to identify unattached or underutilized EBS volumes

**EC2 Instance Connect** - secure way to connect to your instances using SSH

**U2F** is an open authentication standard hosted by the FIDO Alliance - when you enable a U2F security key, you sign in by entering your  credentials and then tapping the device instead of manually entering a  code.

Amazon RedShift - requires a schema

Amazon DynamoDB - schemaless

Under "Data Transfer",  You pay for all bandwidth into and out of Amazon S3, except for the following: (1) Data transferred in from the internet, (2) Data transferred out to  an Amazon Elastic Compute Cloud (Amazon EC2) instance, when the instance is in the same AWS Region as the S3 bucket, (3) Data transferred out to Amazon CloudFront (CloudFront).

AWS RDS Service - **You can use Read Replicas for both improved read performance as well as Disaster Recovery**

 AWS services can be used together to send alerts whenever the AWS account root user signs in - CloudWatch and SNS
To host a static website on Amazon S3, you configure an Amazon S3 bucket for website hosting and then upload your website content to the bucket. When you configure a bucket as a static website, you must enable  website hosting, set permissions, and create and add an index document.



**AWS Storage Gateway** - AWS Storage Gateway is a hybrid cloud storage service that gives you on-premises access to virtually unlimited cloud storage.



When selecting your DR strategy, you must weigh the benefits of lower  RTO (recovery time objective) and RPO (recovery point objective) vs the  costs of implementing and operating a strategy. The pilot light and warm standby strategies both offer a good balance of benefits and cost.

![img](062622%20-%20AWS%20Practice%20Questions.assets/pt4-q56-i1.jpg)

**Global Accelerator** -  is a networking service that helps you improve the availability and  performance of the applications that you offer to your global users

- a good fit for non-HTTP use cases, such as gaming  (UDP), IoT (MQTT), or Voice over IP, as well as for HTTP use cases that  specifically require static IP addresses or deterministic, fast regional failover.

S3 - object storage service - different from block storage service



AWS Shield Advanced includes intelligent DDoS attack detection and  mitigation for not only for network layer (layer 3) and transport layer  (layer 4) attacks but also for application layer (layer 7) attacks.

- not offered much on the managed services

**VPC Interface Endpoint**

An **interface endpoint** is an elastic network interface with a private  IP address from the IP address range of your subnet that serves as an  entry point for traffic destined to a supported service. Interface  endpoints are powered by AWS PrivateLink, a technology that enables you  to privately access services by using private IP addresses. AWS  PrivateLink restricts all network traffic between your VPC and services  to the Amazon network. You do not need an internet gateway, a NAT  device, or a virtual private gateway.

- <u>enables you to privately connect your VPC to an Amazon SQS queue</u>

- ==remember that only S3 and DynamoDB support VPC Endpoint Gateway. All  other services that support VPC Endpoints use a VPC Endpoint Interface.==

**Gateway Endpoint** is a gateway that you specify as a target for a route  in your route table for traffic destined to a supported AWS service. The following AWS services are supported: Amazon S3, DynamoDB. You cannot  use VPC Gateway Endpoint to privately connect your VPC to an Amazon SQS  queue.



