Based on whizlab results: 

==Fault tolerance== is **a process that enables an operating system to respond to a failure in hardware or software**. This fault-tolerance definition refers to the system's ability to continue operating despite failures or malfunctions.

==Network throughput==

In communication networks, **network throughput is the rate of successful  message delivery over a communication channel**, such as Ethernet or  packet radio. The data these messages belong to may be delivered over a  physical or logical link, or it can pass through a certain network node. [Wikipedia](https://en.wikipedia.org/wiki/Network_throughput)

- throughput - the amount of material or items passing through a system or process.

==Consistency Model for DynamoDB==

​      Amazon DynamoDB lets you specify the desired consistency      characteristics for each read request within an application. **You    can specify whether a read is eventually consistent or strongly      consistent.**    

​      The eventual consistency option is the default in Amazon DynamoDB      and maximizes the read throughput. However, an eventually      consistent read might not always reflect the results of a recently      completed write. Consistency across all copies of data is usually      reached within a second.    

​      A strongly consistent read in Amazon DynamoDB returns a result      that reflects all writes that received a successful response prior      to the read. To get a strongly consistent read result, you can      specify optional parameters in a request. It takes more resources      to process a strongly consistent read than an eventually      consistent read. For more information about read consistency, see      [Data       Read and Consistency Considerations](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.ReadConsistency.html).    



With Amazon RDS, you can deploy scalable **MariaDB cloud databases** in minutes with cost-efficient and resizable hardware capacity.

- MariaDB is a popular open source [relational database](https://aws.amazon.com/relational-database/) created by the original developers of MySQL. 



---

[![Image result for Transit gateway aws](060322%20-%20AWS%20self%20study%20session%20based%20on%20whizlab.assets/images.png)](https://www.google.com/search?client=firefox-b-1-d&sxsrf=ALiCzsZumky1xOHHTwD7sFZ0_bYGhIS6qg:1654540665764&q=What+is+a+transit+gateway+in+AWS?&tbm=isch&source=iu&ictx=1&vet=1&fir=cWhYYSODdHV__M%2CQ609DilEUfUHEM%2C_&usg=AI4_-kTHEbVMS2SOjITHGtIscizMfr8X2Q&sa=X&ved=2ahUKEwjuuZilvJn4AhVCtoQIHVNVCyUQ9QF6BAgfEAE#imgrc=cWhYYSODdHV__M)

AWS Transit Gateway **connects your Amazon Virtual Private Clouds (VPCs) and on-premises networks through a central hub**. This simplifies your network and puts an end to complex peering  relationships. It acts as a cloud router – each new connection is only  made once.

### 

A *customer gateway* is a resource that you create in AWS                that represents the customer gateway device in your on-premises network

-  use Amazon VPC with a Site-to-Site VPN 

A *NAT gateway* receives a network interface that's automatically assigned a private IP address from the IP address range of the subne (Network Address Translation)

- ==You can use a NAT gateway    so that **instances in a private subnet can connect to services outside your VPC** but external    services cannot initiate a connection with those instances.==

- **You only need a NAT Gateway if your Lambda function will be accessing the internet**. Assuming that you do need a NAT, you can just use one NAT Gateway for  all your private subnets. All your public subnets must route to an  Internet Gateway for non-local addresses. This is what makes the subnet  public.

**Memory optimized instances** are designed to deliver fast performance for workloads that       process large data sets in memory.

**Amazon API Gateway** is a fully managed service that makes it  easy for developers to create, publish, maintain, monitor, and secure  APIs at any scale. 

**Amazon Simple Queue Service (SQS)** is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications