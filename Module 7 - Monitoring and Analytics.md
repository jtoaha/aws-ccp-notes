5/20/22

# Module 7 - Monitoring and Analytics

## **Learning objectives**

In this module, you will learn how to:

- Summarize approaches to <u>monitoring your AWS environment.</u>
- Describe the benefits of <u>Amazon CloudWatch</u>.
- Describe the benefits of <u>AWS CloudTrail.</u>
- Describe the benefits of <u>AWS Trusted Advisor.</u>

==**Monitoring** - Observing systems, collection metrics, and then using data to make decisions==

- important to set up in the cloud, because of the elastic nature that can scale up and down, you'll want to keep a pulse on AWS resources to ensure systems are running as aspected. For example, 
  - if EC2 instance is being overused, you can trigger a scaling event that automatically creates another EC2 instance
  - or if an application starts sending error responses at an unusually high rate, you can alert an employee to take a look at what is going on.
- variety of tools
  - measure
  - Alert
  - debug and troubleshoot

## **Amazon CloudWatch**

![image-20220520141636344](Module%207%20-%20Monitoring%20and%20Analytics.assets/image-20220520141636344.png)

- ==**Amazon CloudWatch** - Allows you to monitor your AWS infrastructure and your applications you run on AWS in realtime.==

  - It works by <u>tracking and monitoring metrics</u>
    - **metrics**- variables tied to your resources

  - ==**Cloudwatch alarm** - set a threshold for a metric and when that threshold is reached, Cloudwatch can generate and trigger an action==
    - Cloudwatch alarms are integrated with SNS, so you can send SMS notifications to the key person to notify them
  - ==**Cloudwatch's dashboard feature** - if you want to aggregate metrics in a single pane of glass in realtime==

- ==**Benefits of Cloudwatch**==

  - **access all your metrics from a central location**
  - **visibility across applications, infrastructure and service**
    - gain insights across your distributed stacks so you can correlate and visualize metrics and logs to quickly pinpoint and resolve issue
  - **reduce MTTR**(mean time to resolution) **and improve TCO** (total cost of ownership)
    - this means you can free up resources, like freeing up developers, to add business value
  - **drive insights to optimize applications and operational resources**
    - for example, by aggregating usage across an entire fleet of EC2 instances to derive operational and utilization insights

### **Amazon CloudWatch**

==[**Amazon CloudWatch**](https://aws.amazon.com/cloudwatch/) is a web service that enables you to monitor and manage various metrics and configure alarm actions based on data from those metrics.==

CloudWatch uses [**metrics**](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/working_with_metrics.html) to represent the data points for your resources. AWS services send metrics to CloudWatch. CloudWatch then uses these metrics to <u>create graphs automatically that show how performance has changed over time</u>. 

### **CloudWatch alarms**

==With CloudWatch, you can create [**alarms**](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/AlarmThatSendsEmail.html) that automatically perform actions if the value of your metric has gone above or below a predefined threshold.==

For example, suppose that your company’s developers use Amazon EC2 instances for application development or testing purposes. If the developers occasionally forget to stop the instances, the instances will continue to run and incur charges. 

In this scenario, you could <u>create a CloudWatch alarm that automatically stops an Amazon EC2 instance when the CPU utilization percentage has remained below a certain threshold for a specified period</u>. When configuring the alarm, you can specify to receive a notification whenever this alarm is triggered.

### **CloudWatch dashboard**

![CloudWatch dashboard showing metrics for Amazon RDS, Amazon EC2, and Amazon EBS](Module%207%20-%20Monitoring%20and%20Analytics.assets/BrGY0YYp0nrvDKsy_rLfuExSsSpuXOVqf.png)

==The CloudWatch [**dashboard**](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html) feature enables you to access all the metrics for your resources from a single location.== For example, you can use a CloudWatch dashboard to monitor the CPU <u>utilization of an Amazon EC2 instance</u>, the <u>total number of requests made to an Amazon S3 bucket</u>, and more. You can even <u>customize separate dashboards for different business purposes, applications, or resource</u>s.

## Amazon CloudTrail

principle: trust but verify

![image-20220520142919845](Module%207%20-%20Monitoring%20and%20Analytics.assets/image-20220520142919845.png)

==**AWS CloudTrail** - comprehensive AWS auditing tool==

- every request gets logged in the CloudTrail engile
  - Who, when, where (IP address), what was response , did something change, etc
  - How do you prove nothing changed: AWS CloudtTrail
- Cloudtrail - can save those logs indefinitely in secure S3 buckets
  - With tamper proof methods like **vault lock** , you then can show absolute  provenance of all of these critical security audit logs.

### **AWS CloudTrail**

==[**AWS CloudTrail**](https://aws.amazon.com/cloudtrail/) records API calls for your account.== The recorded information includes the <u>identity of the API caller, the time of the API call, the source IP address of the API caller, and more.</u> You can think of CloudTrail as a “trail” of breadcrumbs (or a log of actions) that someone has left behind them.

Recall that <u>you can use API calls to provision, manage, and configure your AWS resources</u>. With CloudTrail, you can view a complete history of user activity and API calls for your applications and resources. 

<u>Events are typically updated in CloudTrail within 15 minutes after an API call.</u> You can <u>filter events</u> by specifying the time and date that an API call occurred, the user who requested the action, the type of resource that was involved in the API call, and more.

### **Example: AWS CloudTrail event**

Suppose that the coffee shop owner is browsing through the AWS Identity and Access Management (IAM) section of the AWS Management Console. They discover that a new IAM user named Mary was created, but they do not know who, when, or which method created the user.

To answer these questions, the owner navigates to AWS CloudTrail.

![Example of details included in a CloudTrail event: what happened, who made the request, when the request occurred, and how the request was made.](Module%207%20-%20Monitoring%20and%20Analytics.assets/8dyh5u6YogoXkmPw_LpdzY_ElDiXoJpKQ.png)

In the CloudTrail Event History section, the owner applies a filter to display only the events for the “CreateUser” API action in IAM. The owner locates the event for the API call that created an IAM user for Mary. This event record provides complete details about what occurred: 

On January 1, 2020 at 9:00 AM, IAM user John created a new IAM user (Mary) through the AWS Management Console.

### **CloudTrail Insights**

==Within CloudTrail, you can also enable [**CloudTrail Insights**](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/logging-insights-events-with-cloudtrail.html).== This optional feature <u>allows CloudTrail to automatically detect unusual API activities</u> in your AWS account. 

For example, CloudTrail Insights might detect that a higher number of Amazon EC2 instances than usual have recently launched in your account. You can then review the full event details to determine which actions you need to take next.

### Knowledge Check

**<u>Which tasks can you perform using AWS CloudTrail? (Select TWO.)</u>**

The correct two response options are:

- **Track user activities and API requests throughout your AWS infrastructure**
- **Filter logs to assist with operational analysis and troubleshooting**

The other response options are tasks that you can perform in Amazon CloudWatch.

- Monitor your AWS infrastructure and resources in real time
- View metrics and graphs to monitor the performance of resources
- Configure automatic actions and alerts in response to metrics

**Learn more:**

- [AWS CloudTrail](https://aws.amazon.com/cloudtrail)

## AWS Trusted Advisor

process should be streamlined, how to save money on overhead, notify of security issues

- Sometimes it's nice to have someone who knows industry best practices

![image-20220520144957688](Module%207%20-%20Monitoring%20and%20Analytics.assets/image-20220520144957688.png)

==AWS Trust Advisor - automated advisor that will evaluate your resources against 5 pillars==: 

1. Cost optimization 
2. Performance
3. Security
4. Fault Tolerance
5. Service Limits 

Trusted Advisor, in real time, runs through a series of checks for each pillar in your account based on AWS best practices and compiles categorized items for you to look into and you can view them direcly in the AWS console .

-  some checks are free, and some need plans
- for example, MFA not turned on, underutilized EC2, EBS volumes that haven't been backed up, etc. 

![image-20220520145705832](Module%207%20-%20Monitoring%20and%20Analytics.assets/image-20220520145705832.png)

![image-20220520145714029](Module%207%20-%20Monitoring%20and%20Analytics.assets/image-20220520145714029.png)

![image-20220520145721829](Module%207%20-%20Monitoring%20and%20Analytics.assets/image-20220520145721829.png)

- red circle - action recommended
- orange triangle - investigatioin recommended
- green square - no detected

![image-20220520145948772](Module%207%20-%20Monitoring%20and%20Analytics.assets/image-20220520145948772.png)

![image-20220520150118516](Module%207%20-%20Monitoring%20and%20Analytics.assets/image-20220520150118516.png)

- ebs volumes without snapshot - if ebs volume fails, you'd lose that data
- Ec2 instances are not properly launched across AZs (deploy across AZs)

![image-20220520150208140](Module%207%20-%20Monitoring%20and%20Analytics.assets/image-20220520150208140.png)

- soft limits - restrictions that can be lifted to some degree
- 5 VPCs - regional limit

Trusted advisor can help you point in the right direction when it comes to 5 pillars

### **AWS Trusted Advisor**

==[**AWS Trusted Advisor**](https://aws.amazon.com/premiumsupport/technology/trusted-advisor/) is a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices.==

<u>Trusted Advisor compares its findings to AWS best practices in five categories: cost optimization, performance, security, fault tolerance, and service limits.</u> For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices. 

The guidance provided by AWS Trusted Advisor can benefit your company at all stages of deployment. For example, you can use AWS Trusted Advisor to assist you while you are creating new workflows and developing new applications. Or you can use it while you are making ongoing improvements to existing applications and resources.

### ***\*AWS Trusted Advisor dashboard\****

![AWS Trusted Advisor dashboard showing the number of items with no problems detected, recommended investigations, and recommended actions for the categories of Cost Optimization, Performance, Security, Fault Tolerance, and Service Limits. Cost Optimization shows $7,516.85 potential monthly savings.](Module%207%20-%20Monitoring%20and%20Analytics.assets/GuvmzlxKCWw8Ltuo_2gGWhu3Np9FWdzHm.jpg)

When you access the Trusted Advisor dashboard on the AWS Management Console, you can review completed checks for cost optimization, performance, security, fault tolerance, and service limits.

For each category:

- The <span style="background-color:#00AA00;">green check</span> indicates the number of items for which it detected **no problems**.
- The <span style="background-color:#AA5500;">orange</span> triangle represents the number of recommended **investigations**.
- The <span style="background-color:#AA0000;">red circle</span> represents the number of recommended **actions**.

## Module 7 Summary

In Module 7, you learned about the following concepts:

- **Amazon CloudWatch** 
  - can provide real time understanding of system behavior
  - look at metrics overtime
- **AWS CloudTrail** 
  - Who dunnit basically
  - answers auditing questions
- **AWS Trusted Advisor**

### Additional resources

To learn more about the concepts that were explored in Module 7, review these resources.

- [Management and Governance on AWS](https://aws.amazon.com/products/management-tools)
- [Monitoring and Observability](https://aws.amazon.com/products/management-tools/use-cases/monitoring-and-observability/)
- [Configuration, Compliance, and Auditing](https://aws.amazon.com/products/management-tools/use-cases/configuration-compliance-and-auditing/)
- [AWS Management & Governance Blog](https://aws.amazon.com/blogs/mt/)
- [Whitepaper: AWS Governance at Scale](https://docs.aws.amazon.com/whitepapers/latest/aws-governance-at-scale/introduction.html)

### Module 7 Quiz

---

**<u>Which actions can you perform using Amazon CloudWatch? (Select TWO.)</u>**

The two correct response options are:

- **Monitor your resources’ utilization and performance**
- **Access metrics from a single dashboard**

The other response options are incorrect because:

- Receiving real-time recommendations for improving your AWS environment can be performed by AWS Trusted Advisor.
- Comparing your infrastructure to AWS best practices in five categories can be performed by AWS Trusted Advisor.
- Automatically detecting unusual account activity can be performed by AWS CloudTrail.

**Learn more:**

- [Amazon CloudWatch](https://aws.amazon.com/cloudwatch)

---

**<u>Which service enables you to review the security of your Amazon S3 buckets by checking for open access permissions?</u>**

The correct response option is **AWS Trusted Advisor**.

 

AWS Trusted Advisor is a web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices. The inspection includes security checks, such as Amazon S3 buckets with open access permissions.

 

The other response options are incorrect because:

- Amazon CloudWatch is a web service that enables you to monitor and manage various metrics for the resources that run your applications.
- AWS CloudTrail is a web service that enables you to review details for user activities and API calls that have occurred within your AWS environment.
- Amazon GuardDuty is a service that provides *<u>intelligent</u>* threat detection for your AWS environment and resources. It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment.

**Learn more:**

- [AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor)

---

**Which categories are included in the AWS Trusted Advisor dashboard? (**Select TWO.)

- The two correct response options are:

  - **Performance**
  - **Fault tolerance**

  AWS Trusted Advisor continuously inspects your AWS environment and provides best practice recommendations across five categories: cost optimization, performance, security, fault tolerance, and service limits.

  

  **Learn more:**

  - [AWS Trusted Advisor](https://aws.amazon.com/premiumsupport/technology/trusted-advisor)

---