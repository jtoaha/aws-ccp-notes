05/31/21

# Module 10 - The Cloud Journey



## **Learning objectives**

In this module, you will learn how to:

- Summarize the five pillars of the Well-Architected Framework.  
- Explain the six benefits of cloud computing.

<video class="vjs-tech" poster="https://assets.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1654020000/_RO3tQ4UHCTrOQFdPob5pQ/tincan/31d9c0cca79c54bdceaf3e938fd424e97c98c7e8/assets/fsOvy_d2Ek9vSZpO_transcoded-H6k5c3f4GC1hZsai-T9C01-Intro_V02_Final-00001.png" crossorigin="anonymous" id="vjs_video_3_html5_api" tabindex="-1" preload="none" src="https://assets.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1654020000/_RO3tQ4UHCTrOQFdPob5pQ/tincan/31d9c0cca79c54bdceaf3e938fd424e97c98c7e8/assets/EfHS_4SoLkeBTttA_transcoded-H6k5c3f4GC1hZsai-T9C01-Intro_V02_Final.mp4?v=1" style="box-sizing: inherit; margin: 0px; padding: 0px; border: 0px; font: inherit; vertical-align: initial; width: 757px; height: 425.812px; position: absolute; top: 0px; left: 0px;"></video>

Play Video

Video transcript

+

 









Use each individual service as building blocks

Countless architectures, how do you know 



![image-20220531114030142](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531114030142.png)

![image-20220531114046335](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531114046335.png)

- important fo reliability
- important to detect deficiencies like in this simple example, though not all examples are simple
- There are tools that can help you: Well-architected Framework

Pillars: 

1. Operational  Excellence
2. Security
3. Reliability
4. Performance
5. Cost Optimization

## The AWS Well-Architected Framework



![image-20220531120517262](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531120517262.png)

**Well-architected Framework - designed to enable architects, developers, and users of AWS  to build secure, high performing, resilient and efficient infrastructure for their applications.** Compose of five pillars to ensure consistent approach to reviewing and designing of architectures

1. **Operational  Excellence** - fcouses on running and monitoring systems to deliver buisness value and continually improving processes and procedures. 
   - for example, automating changes with deployment pipelines
   - or responding to events that are triggered
2. **Security** - priority number 1, checks integrity of data and protecting systems via encryption
3. **Reliability** - recovery planning, example from DynamoDB disruption or EC2 node failure to how you handle change to  meet business and customer demand
4. **Performance** - entails using it and computing resources efficiently
   - using right EC2 type and making informed decisions
5. **Cost Optimization** - 
   - you nee

![image-20220531120725759](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531120725759.png)

Framework released as a self-service tool

- Access it via AWS management console, create a workload, run it against your was account, to generate a report which reports potential issues and suggestions based on well established practices

==In South Africa, traffic lights are called robots==

 ![image-20220531120837711](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531120837711.png)

### **The AWS Well-Architected Framework**

The [**AWS Well-Architected Framework**](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf) helps you understand how to design and operate reliable, secure, efficient, and cost-effective systems in the AWS Cloud. It provides a way for you to consistently measure your architecture against best practices and design principles and identify areas for improvement.

![Icons to represent the five pillars of the AWS Well-Architected Framework: Operational excellence, Security, Reliability, Performance efficiency, and Cost optimization](Module%2010%20-%20The%20Cloud%20Journey.assets/JAG1LhejYvICxV_N_GfjpKo2tSEh9ACeE.png)

The Well-Architected Framework is based on five pillars: 

- Operational excellence
- Security
- Reliability
- Performance efficiency
- Cost optimization

To learn more, select the **+** symbol next to each category.

Operational excellence

–

<u>**Operational excellence** is the ability to run and monitor systems to deliver business value and to continually improve supporting processes and procedures.</u>  



Design principles for operational excellence in the cloud include performing operations as code, annotating documentation, anticipating failure, and frequently making small, reversible changes.

Security

–

<u>The **Security** pillar is the ability to protect information, systems, and assets while delivering business value through risk assessments and mitigation strategies.</u> 



When considering the security of your architecture, apply these best practices:

- <u>Automate</u> security best practices when possible.
- <u>Apply security at all layers.</u>
- <u>Protect data in transit and at rest.</u>

Reliability

–

**<u>Reliability** is the ability of a system to do the following:</u>

- Recover from infrastructure or service disruptions
- Dynamically acquire computing resources to meet demand
- Mitigate disruptions such as misconfigurations or transient network issues

Reliability includes testing recovery procedures, scaling horizontally to increase aggregate system availability, and automatically recovering from failure.

Performance efficiency

–

**Performance efficiency** is the ability to use computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve. 



Evaluating the performance efficiency of your architecture includes experimenting more often, using serverless architectures, and designing systems to be able to go global in minutes.

Cost optimization

–

<u>**Cost optimization** is the ability to run systems to deliver business value at the lowest price point.</u> 



Cost optimization includes adopting a consumption model, analyzing and attributing expenditure, and using managed services to reduce the cost of ownership.

---

**<u>Which pillar of the AWS Well-Architected Framework focuses on the ability of a workload to consistently and correctly perform its intended functions?</u>**

The correct response option is **Reliability**. 

The other response options are incorrect because:

- The <u>Operational Excellence</u> pillar includes the ability to run workloads effectively, gain insights into their operations, and continuously improve supporting processes to deliver business value.
- The <u>Performance Efficiency</u> pillar focuses on using computing resources efficiently to meet system requirements, and to maintain that efficiency as demand changes and technologies evolve.
- The <u>Security</u> pillar includes protecting data, systems, and assets, and using cloud technologies to improve the security of your workloads.

**Learn more:**

- [Whitepaper: AWS Well-Architected Framework](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf)

---

## Benefits of the AWS Cloud

AWS Services - building blocks, scale, flexible reliable

AWS terminology - 

6 main benefits of using the AWS Cloud - can help you make decisions in an informed way

This is a super important thing to remember. 

Trade fixed expense for variable expense. 

1. Trade fixed 

   ![image-20220531122426193](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531122426193.png)

   ![image-20220531122306428](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531122306428.png)	You can start small with AWS

   ![image-20220531122515049](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531122515049.png)

​	2. Benefit from massive a

- ![image-20220531122701533](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531122701533.png)
  - in order to build data centers, AWS is buying huge amounts of hardware and are experts at building efficient data centers. 
  - Can buy hardware at a lower price because of massive volume   
  - ![image-20220531122954830](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531122954830.png)

3. Stop guessing capacity

   - ![image-20220531123013701](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531123013701.png)
   - with AWS, you don't need to guess
   - ![image-20220531123317211](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531123317211.png)

4. Increase speed and agility

   - ![image-20220531123326140](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531123326140.png)

   - it's easy to try new things

     ![image-20220531123445559](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531123445559.png)

     - flexibility of AWS helps drive innovation
     - takes minutes to set up compared to weeks
     - helps you get to market quicker

5. ![image-20220531123536281](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531123536281.png)

   - what makes your offering better than your competitors
   - delight your customers with new innovative solutions

6. Go global in minutes

7. - ![image-20220531123615356](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531123615356.png)
   - ![image-20220531123653551](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531123653551.png)
   - ![image-20220531123916067](Module%2010%20-%20The%20Cloud%20Journey.assets/image-20220531123916067.png)

   

   ## **Advantages of cloud computing**

   Operating in the AWS Cloud offers many benefits over computing in on-premises or hybrid environments. 

   **In this section, you will learn about six advantages of cloud computing:**

   - **Trade upfront expense for variable expense.**
   - **Benefit from massive economies of scale.**
   - **Stop guessing capacity.**
   - **Increase speed and agility.**
   - **Stop spending money running and maintaining data centers.**
   - **Go global in minutes.**

   To learn more, select the **+** symbol next to each category.



<u>**Trade upfront expense for variable expense.**</u>

–

Upfront expenses include data centers, physical servers, and other resources that you would need to invest in before using computing resources. 



Instead of investing heavily in data centers and servers before you know how you’re going to use them, <u>you can pay only when you consume computing resources.</u>

<u>**Benefit from massive economies of scale.**</u>

–

<u>By using cloud computing, you can achieve a lower variable cost than you can get on your own.</u> 

Because usage from hundreds of thousands of customers aggregates in the cloud, providers such as AWS can achieve higher economies of scale. Economies of scale translate into lower pay-as-you-go prices.

**<u>Stop guessing capacity.</u>**

–

With cloud computing, you don’t have to predict how much infrastructure capacity you will need before deploying an application. 

For example, you can launch Amazon Elastic Compute Cloud (Amazon EC2) instances when needed and pay only for the compute time you use. Instead of paying for resources that are unused or dealing with limited capacity, <u>you can access only the capacity that you need, and scale in or out in response to demand.</u> 

<u>**Increase speed and agility.**</u>

–

The flexibility of cloud computing makes it easier for you to develop and deploy applications.

This flexibility also provides your development teams with <u>more time to experiment and innovate.</u>

<u>**Stop spending money running and maintaining data centers.**</u>

–

Cloud computing in data centers often requires you to spend more money and time managing infrastructure and servers. 



A benefit of cloud computing is the ability to focus less on these tasks and more on your applications and customers.

<u>**Go global in minutes.**</u>

–

The AWS Cloud global footprint enables you to <u>quickly deploy applications to customers around the world, while providing them with low latency</u>.

---

<u>**Which process is an example of benefiting from massive economies of scale?**</u>

The correct response option is: **Receiving lower pay-as-you-go prices as the result of AWS customers’ aggregated usage of services**.

 

Because usage from hundreds of thousands of customers is aggregated in the cloud, providers such as AWS can achieve higher economies of scale. The economies of scale translate into lower pay-as-you-go prices. 

 

The other response options are incorrect because:

- Deploying an application in multiple Regions around the world: This process is an example of *Go global in minutes*.
- Paying for compute time as you use it instead of investing upfront costs in data centers: This process is an example of *Trade upfront expense for variable expense*.
- Scaling your infrastructure capacity in and out to meet demand: This process is an example of *Stop guessing capacity*.

**Learn more:**

- [Six advantages of cloud computing](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/six-advantages-of-cloud-computing.html)

 

## Summary

In Module 10, you learned about the following concepts:

- The five pillars of the AWS Well-Architected Framework:
  - Operational excellence
  - Security
  - Reliability
  - Performance efficiency
  - Cost optimization
- Six advantages of cloud computing:
  - Trade upfront expense for variable expense.
  - Benefit from massive economies of scale.
  - Stop guessing capacity.
  - Increase speed and agility.
  - Stop spending money running and maintaining data centers.
  - Go global in minutes.

### **Additional resources**

To learn more about the concepts that were explored in Module 10, review these resources.

- [AWS Well-Architected](https://aws.amazon.com/architecture/well-architected/)

- [Whitepaper: AWS Well-Architected Framework](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf)

- [AWS Architecture Center](https://aws.amazon.com/architecture)

- [Six Advantages of Cloud Computing](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/six-advantages-of-cloud-computing.html)

- [AWS Architecture Blog](https://aws.amazon.com/blogs/architecture)

  

----

**<u>Which pillar of the AWS Well-Architected Framework includes the ability to run workloads effectively and gain insights into their operations?</u>**

The correct response option is **Operational Excellence**.

The other response options are incorrect because:

- The **<u>Cost Optimization</u>** pillar focuses on the ability to run systems to deliver business value at the lowest price point.
- The **<u>Performance Efficiency</u>** pillar focuses on using computing resources efficiently to meet system requirements and to maintain that efficiency as demand changes and technologies evolve.
- The **<u>Reliability</u>** pillar focuses on the ability of a workload to consistently and correctly perform its intended functions.

---

<u>**What are the benefits of cloud computing? (Select TWO.)**</u>

- 
  Increase speed and agility.

  Correctly checked

- 

  Benefit from smaller economies of scale.

  Correctly unchecked

- 

  Trade variable expense for upfront expense.

  Correctly unchecked

- 

  Maintain infrastructure capacity.

  Incorrectly checked

- 

  Stop spending money running and maintaining data centers.

The two correct response options are: 

- **Increase speed and agility.**
- **Stop spending money running and maintaining data centers.**

The six advantages of cloud computing are:

- Trade upfront expense for variable expense.
- Benefit from massive economies of scale.
- Stop guessing capacity.
- Increase speed and agility.
- Stop spending money running and maintaining data centers.
- Go global in minutes.

**Learn more:**

- [Six advantages of cloud computing](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/six-advantages-of-cloud-computing.html)



