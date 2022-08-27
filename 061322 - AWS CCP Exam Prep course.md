06/13/22

# AWS Certified Cloud Practitioner Foundations Exam Prep

AWS Cloud and its value proposition: 

1. AWS Cloud - 
   - **Security**: ability to contorl and automate actions based on events, benefits of  enforce security standards for users and more
     -  IAM and security groups
   -  **high availability infrastructure** - AZ, regions, ELB, Route 53

**value proposition: allows you to focus on busines value**

- how utilizing AWS can help you shift away from on-premises infrastructure management
- able to prioritize: optimize resource utilization, efficient applications, better user experience, etc that can help generate more revenue

 

----

Economy of scale - about buying power

High availability - about resiliency and avoiding single points of failure

Agility - is abillity to add and remove existing services quickly and easily

==**AWS Cloud Economics** - how operating in AWS can affect your organization's ownership and operational costs==

- TCO: 
  - ![image-20220613110951645](061322%20-%20AWS%20CCP%20Exam%20Prep%20course.assets/image-20220613110951645.png)
  - **Opex** - day to day costs, ex. printer toner, etc, costs necessary to keep going
  - **Capex** - cost associated with longer term expenses (pruchased once and expected to last)
  - **Labor costs** - network op technicians
  - **impact of software licensing costs** - current software
- **which operations will reduce cost by  to the cloud**
  - evaluating what is necessary, looking for other ways to meet demand, autoscaling is a helpful service
  - utilizing data segmentation, reduce scope of complaince and save time during audits
  - ![image-20220613111237709](061322%20-%20AWS%20CCP%20Exam%20Prep%20course.assets/image-20220613111237709.png)

![image-20220613111939533](061322%20-%20AWS%20CCP%20Exam%20Prep%20course.assets/image-20220613111939533.png)

- Design for failure - what and how components fail and how to architect around it
  - 2 servers instead of single server
- monolithic architecture - improving and updating can be more complex
  - decoupling components such as application and database allows them to be scaleld and managed based on their individual needs
  - implementation of elasticity in the cloud vs on premise
- elasticity is a common reason for building in the cloud
- **Think parallel** - serial and sequential processing. dependencies can make or break entire processes
  - divide a job and distribute to multiple components to handle demand\
  - if servers are processing all requests sequentially, will only be able to handle a limited number and subsequent requests are on hold 

==Designing for failure, decoupling components, implementing elasticity,  thinking parallel are cloud architecture design principles==

This credential helps organizations identify and develop talent with critical knowledge related to implementing cloud initiatives. Earning AWS Certified Cloud Practitioner validates cloud fluency and foundational knowledge of Amazon Web Services (AWS).

To learn more, see: [AWS Certified Cloud Practitioner](https://aws.amazon.com/certification/certified-cloud-practitioner/)

To earn this certification, you need to take and pass the AWS Certified Cloud Practitioner exam. The exam features a combination of two question formats: multiple choice and multiple response. Additional information, such as a detailed exam content outline, is in the exam guide.

To learn more, see: [AWS Certified Cloud Practitioner Exam Guide](https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide.pdf)

==**Cloud computing provides a simpler way to access servers, storage, databases and a broad set of application services over the internet**. A cloud services provider, such as AWS, owns and maintains the network-connected hardware required for these application services, while you provision and use what you need via a web application. This style of computing offers many benefits that can help your business.==

To learn more, see: [Six Advantages of Cloud Computing](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/six-advantages-of-cloud-computing.html)

When you first start, AWS can seem overwhelming. A cloud-native paradigm of building infrastructure can be a radical departure from the traditional on-premises way of doing things. And regardless, if this is your first time working with infrastructure—or you've been tuning Linux kernels for the last decade—it can be hard to know where to start.

To learn more, see: [AWS Fundamentals - Core Concepts](https://aws.amazon.com/getting-started/fundamentals-core-concepts/)

==AWS Cloud Economics developed the Cloud Value Framework to help organizations build a comprehensive business case for cloud by measuring and tracking progress against four key dimensions of value: cost savings, staff productivity, operational resilience, and business agility==. This paper shares how the AWS Cloud is transforming business and provides an analysis of these four aspects of business value.

To learn more, see: [Business Value on AWS](https://aws.amazon.com/executive-insights/content/business-value-on-aws/)

AWS offers a couple of tools geared towards cost and pricing evaluation. If the workload details and services to be used are identified, the AWS Pricing Calculator can help you calculate the total cost of ownership. Migration Evaluator helps you inventory your existing environment, identify workload information, and design and plan your AWS migration.

To learn more, see: [AWS Pricing/TCO Tools](https://docs.aws.amazon.com/whitepapers/latest/how-aws-pricing-works/aws-pricingtco-tools.html)

Rightsizing is the process of matching instance types and sizes to your workload performance and capacity requirements at the lowest possible cost. It’s also the process of looking at deployed instances and identifying opportunities to remove or downsize them without compromising capacity or other requirements, which results in lower costs.

To learn more, see: [Optimizing your cost with Rightsizing Recommendations](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/ce-rightsizing.html)

AWS Well-Architected helps cloud architects build secure, high-performing, resilient, and efficient infrastructure for their applications and workloads. Based on five pillars—operational excellence, security, reliability, performance efficiency, and cost optimization—AWS Well-Architected provides a consistent approach for customers and AWS Partners to evaluate architectures, and implement designs that can scale over time.

To learn more, see: [AWS Well-Architected](https://aws.amazon.com/architecture/well-architected/?wa-lens-whitepapers.sort-by=item.additionalFields.sortDate&wa-lens-whitepapers.sort-order=desc)

When you architect technology solutions on AWS, if you neglect the five pillars of operational excellence, security, reliability, performance efficiency, and cost optimization, it can become challenging to build a system that delivers on your expectations and requirements. Incorporating these pillars into your architecture helps produce stable and efficient systems. You can then focus on the other aspects of design, such as functional requirements.

To learn more, see: [The 5 Pillars of the AWS Well-Architected Framework](https://aws.amazon.com/blogs/apn/the-5-pillars-of-the-aws-well-architected-framework/)

## AWS: Security and Compliance

Shared Responsibility Model

![image-20220613115129531](061322%20-%20AWS%20CCP%20Exam%20Prep%20course.assets/image-20220613115129531.png)

- You should know when you need to secure resources 
- What security features exists and when responsible for enabling

AWS responsible for security of the cloud and customer is responsible for security in the cloud.

==Customer's responsibility shifts based on the service they're using==

- patching DB instance - AWS responsible
- EC2 patching - customer responsible
- it all depends on whether it's managed or not

![image-20220614141058514](061322%20-%20AWS%20CCP%20Exam%20Prep%20course.assets/image-20220614141058514.png)

Managed vs unmanaged IAM policies - AWS creates Managed policie

