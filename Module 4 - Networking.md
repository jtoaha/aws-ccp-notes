5/11/22

# Module 4: Networking

## **Learning objectives**

In this module, you will learn how to:

- Describe the <u>basic concepts of networking.</u>
- Describe the difference between <u>public and private networking resources</u>. 
- Explain a <u>virtual private gateway</u> using a real life scenario. 
- Explain a <u>virtual private network</u> (VPN) using a real life scenario.
- Describe the benefit of <u>AWS Direct Connect</u>. 
- Describe the benefit of hybrid deployments. 
- Describe the l<u>ayers of security used in an IT strategy</u>.
- Describe the services customers use to interact with the <u>AWS global network</u>.

![image-20220511150826881](Module%204%20-%20Networking.assets/image-20220511150826881.png)



Amazon Virtual Private Cloud (VPC) - allows to proivsion a logically isolate section of the AWS Cloud where you can launch AWS resources in a virtual network that you define. 

- can be public facing - internet access
- private - no internet access
- **Subnet** - public and private grouping of networks.  
  - They are ranges of ip addresses in your VPC

## <u>Connectivity to AWS</u>

VPC - is your own VPN in AWS

- A VPC allows you to define your private IP range for your AWS resources, and you place things like EC2 instances and ELBs inside of your VPC
- You place resources into different subnets (chunks of IP addres allow you group resources together)
- You can control what traffics get into your VPC at all.
  - public website : public can reach
  - internal resources like NHR applications, backend database: resources you only want to be reachable if someone is logged into your private network

**<u>Public Facing resources:</u>** 

![image-20220511151613701](Module%204%20-%20Networking.assets/image-20220511151613701.png)

- ==**Internet Gateway**== is like a doorway that is open to the public 
  - without it no one can reach the resources placed inside your VPC

**<u>A VPC with all internal private resources:</u>** 

![image-20220511152243386](Module%204%20-%20Networking.assets/image-20220511152243386.png)

- because we don't want anyone to access our resources inside a VPC, we don't want to use an Internet Gateway, instead we want to a private gateway that only allows people to come in only when they are coming in from an approved network (not public internet) -> ==Virtual Private Gateway==

  - it allows you to create a VPN connection between a private network, like your on-premises data center or your internal corporate network, to your VPC

  - VPN Connections are private and encrypted, but still use a regular internet connection that is shared

  - You want the lowest amount of latency possible, and your connection to not be shared with anyone else with the highest amount of security possible :

    ![image-20220511152900854](Module%204%20-%20Networking.assets/image-20220511152900854.png)

    - Can be achieved with ==**AWS Direct Connect:** it allows you to establish a completely private, dedicated fiber connection from your data center to AWS==
      - You work with a Direct Connect partner in your area to establish this connection, because like my magic doorway, **AWS Direct Connect provides a physical line that connects your network to your AWS VPC**.
      - This can help you meet high regulatory and compiance need and potentially side-step bandwidth issues
      - **One VPC might have multiple types of gateways attached for multiple types of resources, all residing in same VPC, just in different subnets**

### **Amazon Virtual Private Cloud (Amazon VPC)**

Imagine the millions of customers who use AWS services. Also, imagine the millions of resources that these customers have created, such as Amazon EC2 instances. Without boundaries around all of these resources, network traffic would be able to flow between them unrestricted. 

A networking service that you can use to establish boundaries around your AWS resources is [**Amazon Virtual Private Cloud (Amazon VPC)**](https://aws.amazon.com/vpc/).

==Amazon VPC enables you to provision an isolated section of the AWS Cloud.== 

- In this isolated section, you can launch resources in a virtual network that you define. 
- Within a virtual private cloud (VPC), you can organize your resources into subnets. 
  - ==A **subnet** is a section of a VPC that can contain resources such as Amazon EC2 instances.==

### **Internet gateway**

To allow public traffic from the internet to access your VPC, you attach an **internet gateway** to the VPC.

![image-20220511154646313](Module%204%20-%20Networking.assets/image-20220511154646313.png)

**An ==internet gateway== is a connection between a VPC and the internet. Y**ou can think of an internet gateway as being similar to a doorway that customers use to enter the coffee shop. **Without an internet gateway, no one can access the resources within your VPC**.

### **Virtual private gateway**

To access private resources in a VPC, you can use a **virtual private gateway**. 

![image-20220511154837040](Module%204%20-%20Networking.assets/image-20220511154837040.png)

Here’s an example of how a virtual private gateway works. You can think of the internet as the road between your home and the coffee shop. Suppose that you are traveling on this road with a bodyguard to protect you. You are still using the same road as other customers, but with an extra layer of protection. 

==The bodyguard is like a virtual private network (VPN) connection that encrypts (or protects) your internet traffic from all the other requests around it.==

**The virtual private gateway is the component that allows protected internet traffic to enter into the VPC**. Even though your connection to the coffee shop has extra protection, traffic jams are possible because you’re using the same road as other customers. 

A **virtual private gateway enables you to establish a virtual private network (VPN) connection between your VPC and a private network**, such as an on-premises data center or internal corporate network. A virtual private gateway <u>allows traffic</u> into the VPC only if it is coming <u>from an</u> <u>approved network</u>.

### **AWS Direct Connect**

==[**AWS Direct Connect**](https://aws.amazon.com/directconnect/) is a service that enables you to establish a dedicated private connection between your data center and a VPC.==

Suppose that there is an apartment building with a hallway directly linking the building to the coffee shop. Only the residents of the apartment building can travel through this hallway. 

This private hallway provides the same type of dedicated connection as AWS Direct Connect. Residents are able to get into the coffee shop without needing to use the public road shared with other customers. 

![image-20220511155048560](Module%204%20-%20Networking.assets/image-20220511155048560.png)

The **private connection that AWS Direct Connect** provides helps you to **reduce network costs** and i**ncrease the amount of bandwidth** that can travel through your network.

## Subnets and network access control lists

![image-20220511155441535](Module%204%20-%20Networking.assets/image-20220511155441535.png)

AWS has a wide range of tools that cover every layer of security: network hardening, application security, user identity, authentication and authorization, distributed denial-of-service or DDoS prevention, data integrity, encryption, much more

![image-20220511155811634](Module%204%20-%20Networking.assets/image-20220511155811634.png)

Network hardening 

The only technical reason for using subnets in the VPC is to control access to the gateways

- The public subnets have access to the internet gateway, and the private subnets do not

- The subnets can also control traffic permissions.

  ![image-20220511155855426](Module%204%20-%20Networking.assets/image-20220511155855426.png)

  - Every packet gets checked against a ==**network access control list (Network ACL)**==

    - Network ACLs check traffic going into and leaving a a subnet
    - Requests such an unapproved administrative requests get blocked before they ever touch their target
    - A Network ACL only gets to check packets if it crosses a subnet boundary 

  - But it doesn't evaluate whether it can access a specific EC2 instance or not. Each EC2 instance might have different rules about who and what can access it, so ==**we need instance-level network security as well**==

    ![image-20220511160526695](Module%204%20-%20Networking.assets/image-20220511160526695.png)

    - For instance-level security we have ==security groups==

      ![image-20220511160749772](Module%204%20-%20Networking.assets/image-20220511160749772.png)

      - **==Security groups== by default does not allow any traffic at all (ip addresses, all ports, etc are blocked)**

        - that's very secure but not useful

        - <u>You can modify the security group to accept a different type of traffic:</u>

          - Example: Https allowed (but no os or administrative requests):

            ![image-20220511160856762](Module%204%20-%20Networking.assets/image-20220511160856762.png)

        - <u>Security groups allow specific traffic in, and allows all traffic to go out</u>

        - 

    - **Key difference:** <u>security group is stateful</u> (has memory) and <u>network acl is stateless</u> (doesn't remember)![image-20220511161306761](Module%204%20-%20Networking.assets/image-20220511161306761.png)

      - Traffic management doesn't care about contents of packet itself (it doesn't even open envelope), all it can do is check to see if sender is on the approved list

    - Example: Same VPC, different subnets

      ![image-20220511161738520](Module%204%20-%20Networking.assets/image-20220511161738520.png)

      

      - ​	packet leaves EC2 instance (security group doesn't check outgoing traffic) and then the packet must pass through the NetworkACL which does check outgoing traffic. Exit original subnet. Now packet goes to target subnet, where it needs to be approved by a network acl as well, and approaches EC2 instance , must pass through security group

      - Once transaction complete, <u>packet must return home</u>

        - Every ingress and egress is checked with the appropriate list. 

          - stateless controls, means network ACLs, always checks it's lists. 

          ![image-20220511162233559](Module%204%20-%20Networking.assets/image-20220511162233559.png)

          - <u>Security group recognizes the packet from before so it do esn't need ot check to see if it's allow in</u>

          - Packets going from instance to instance actually happens instantaneously 
            - Technology that makes that possible under the hood
          - Good network security will take advantage of network ACLs and security groups because security in depth is critical for modern architectures

To learn more about the role of subnets within a VPC, review the following example from the coffee shop.

First, customers give their orders to the cashier. The cashier then passes the orders to the barista. This process allows the line to keep running smoothly as more customers come in. 

Suppose that some customers try to skip the cashier line and give their orders directly to the barista. This disrupts the flow of traffic and results in customers accessing a part of the coffee shop that is restricted to them.

![image-20220511180902545](Module%204%20-%20Networking.assets/image-20220511180902545.png)

To fix this, the owners of the coffee shop divide the counter area by placing the cashier and the barista in separate workstations. The cashier’s workstation is public facing and designed to receive customers. The barista’s area is private. The barista can still receive orders from the cashier but not directly from customers.

![image-20220511180924650](Module%204%20-%20Networking.assets/image-20220511180924650.png)

This is similar to how <u>you can use AWS networking services to isolate resources and determine exactly how network traffic flows.</u>

In the coffee shop, you can think of the counter area as a VPC. The counter area divides into two separate areas for the cashier’s workstation and the barista’s workstation. <u>In a VPC, **subnets** are separate areas that are used to group together resources.</u>

### Subnets

<u>A subnet is a section of a VPC in which you can group resources based on security or operational needs.</u> Subnets can be public or private. 

![Architecture diagram of a VPC with three Amazon EC2 instances in a public subnet and three databases in a private subnet](Module%204%20-%20Networking.assets/-HQN-9SqkWc5e-yv_pi4TpfvEYaalWuIu.png)

**Public subnets** contain resources that need to be accessible by the public, such as an <u>online store’s website</u>.

**Private subnets** contain resources that should be accessible only through your private network, such as a <u>database that contains customers’ personal information and order histories</u>. 

<u>In a VPC, subnets can communicate with each other.</u> For example, you might have an application that involves Amazon EC2 instances in a public subnet communicating with databases that are located in a private subnet.

### **Network traffic in a VPC**

When a customer requests data from an application hosted in the AWS Cloud, this request is sent as a packet. A **packet** is a unit of data sent over the internet or a network. 

<u>It enters into a VPC through an internet gateway</u>. <u>Before a packet can enter into a subnet or exit from a subnet, it checks for permissions</u>. These <u>permissions</u> indicate <u>who sent the packet</u> and <u>how the packet is trying to communicate with the resources in a subn</u>et.

The VPC component that checks packet permissions for subnets is a [**network access control list (ACL)**](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html).

### **Network access control lists (ACLs)**

==A network access control list (ACL) is a virtual firewall that controls inbound and outbound traffic at the <u>subnet level</u>.==

For example, step outside of the coffee shop and imagine that you are in an airport. In the airport, travelers are trying to enter into a different country. You can think of the travelers as packets and the passport control officer as a network ACL. The passport control officer checks travelers’ credentials when they are both entering and exiting out of the country. If a traveler is on an approved list, they are able to get through. However, if they are not on the approved list or are explicitly on a list of banned travelers, they cannot come in.

![Architecture diagram of a network access control list in front of a public subnet](Module%204%20-%20Networking.assets/Iw1uUP_PAhIJktew_e5z0Nx1wJ-H36Lsd.png)

==<u>Each AWS account includes a default network ACL</u>. When configuring your VPC, you can use your account’s **default network ACL** or **create custom network ACLs**.==

By default, your account’s <u>**default network ACL** allows all inbound and outbound traffic</u>, but you can modify it by adding your own rules. For **<u>custom network ACLs</u>**, <u>all inbound and outbound traffic is denied until you add rules to specify which traffic to allow</u>. Additionally, **all network ACLs have an explicit deny rule.** This rule <u>ensures that if a packet doesn’t match any of the other rules on the list, the packet is denied</u>. 

### **Stateless packet filtering**

==Network ACLs perform **stateless** packet filtering.== They <u>remember nothing and check packets that cross the subnet border each way</u>: inbound and outbound. 

Recall the previous example of a traveler who wants to enter into a different country. This is similar to sending a request out from an Amazon EC2 instance and to the internet.

When a packet response for that request comes back to the subnet, the network ACL does not remember your previous request. <u>The network ACL checks the packet response against its list of rules to determine whether to allow or deny.</u>

![Illustration of a traveler requesting to enter and then exit; for both requests, the passport control offer checks to ensure the traveler is on the list.](Module%204%20-%20Networking.assets/-IqvewqIwJScqVre_y7vKKj12R8wZy8gK.png)

After a packet has entered a subnet, it must have its permissions evaluated for resources within the subnet, such as Amazon EC2 instances. 

==The VPC component that checks packet permissions for an Amazon EC2 instance is a [**security group**](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html).==

### Security groups

==A security group is a virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance.==

![Architecture diagram of a security group in front of an Amazon EC2 instance](Module%204%20-%20Networking.assets/C6j8UBusL2YCM61I_s3gZMSNIJWunc8qs.png)

==<u>By default, a security group denies all inbound traffic and allows all outbound traffic</u>. You can add custom rules to configure which traffic to allow or deny.==

For this example, suppose that you are in an apartment building with a door attendant who greets guests in the lobby. You can think of the guests as packets and the door attendant as a security group. As guests arrive, the door attendant checks a list to ensure they can enter the building. However, the door attendant does not check the list again when guests are exiting the building

<u>If you have multiple Amazon EC2 instances within a subnet, you can associate them with the same security group or use different security groups for each instance.</u> 

### **Stateful packet filtering**

==Security groups perform **stateful** packet filtering. They remember previous decisions made for incoming packets.==

Consider the same example of sending a request out from an Amazon EC2 instance to the internet. 

<u>When a packet response for that request returns to the instance, the security group remembers your previous request.</u> <u>The security group allows the response to proceed, regardless of inbound security group rules.</u>

![Illustration of a guest requesting to enter and then exit; the door attendant remembers the initial approval and allows the guest to exit without checking the list again.](Module%204%20-%20Networking.assets/nf1lZAA-I6EQxVy1_unCx4hVGemR5ybFS.png)

==Both network ACLs and security groups enable you to configure custom rules for the traffic in your VPC.=== As you continue to learn more about AWS security and networking, make sure to understand the differences between network ACLs and security groups.

==Question: Does this hold true for an instance that travels across different vpcs and then returns? Probably not but holds true at least for a packet returning to an instance within the same vpc==

![image-20220511182041097](Module%204%20-%20Networking.assets/image-20220511182041097.png)

![image-20220511182437403](Module%204%20-%20Networking.assets/image-20220511182437403.png)

Which statement best describes an AWS account’s default network access control list?

- It is stateless and allows all inbound and outbound traffic.

Correct

The correct response option is **It is stateless and allows all inbound and outbound traffic**.

 

Network access control lists (ACLs) perform **stateless** packet filtering. They remember nothing and check packets that cross the subnet border each way: inbound and outbound.

 

Each AWS account includes a default network ACL. When configuring your VPC, you can use your account’s default network ACL or create custom network ACLs.

 

By default, your account’s default network ACL allows all inbound and outbound traffic, but you can modify it by adding your own rules. For custom network ACLs, all inbound and outbound traffic is denied until you add rules to specify which traffic should be allowed. Additionally, all network ACLs have an explicit deny rule. This rule ensures that if a packet doesn’t match any of the other rules on the list, the packet is denied.

---

## Global Networking

How do customers interact with AWS infrastructure? They enter a URL and site opens up. But how does that work? 

![image-20220511182950042](Module%204%20-%20Networking.assets/image-20220511182950042.png)

Route 53 - Amazon's DNS service

- DNS - a translation service  that translates website names to ip addresses

![image-20220511183226401](Module%204%20-%20Networking.assets/image-20220511183226401.png)

So, when you enter this url, it contacts Route 53 to obtain IP address, and then Route 53 directs your browser to this IP address, and can be routed based on different policies

![image-20220511183315157](Module%204%20-%20Networking.assets/image-20220511183315157.png)

- Geolocation DNS - direct traffic based on where customer is located in 
- You can even use Route 53 to register domain names

![image-20220511183433022](Module%204%20-%20Networking.assets/image-20220511183433022.png)

- can help speed up delivery of website assets to customers, Amazon CloudFront
  - via CDNs

### **Domain Name System (DNS)**

Suppose that AnyCompany has a website hosted in the AWS Cloud. Customers enter the web address into their browser, and they are able to access the website. This happens because of **Domain Name System (DNS)** resolution. ==DNS resolution involves a customer DNS resolver communicating with a company DNS server.==

<u>You can think of DNS as being the phone book of the internet.</u> ==DNS resolution is the process of translating a domain name to an IP address.==

![Process diagram of DNS resolution](Module%204%20-%20Networking.assets/Pd32jad3VWk7EjGe_AFBIDcTkYnYj1OOb.png)

For example, suppose that you want to visit AnyCompany’s website. 

- 1

  1

  When you enter the domain name into your browser, this request is sent to a customer DNS resolver. 

- 2

  2

  The customer DNS resolver asks the company DNS server for the IP address that corresponds to AnyCompany’s website.

- 3

  3

  The company DNS server responds by providing the IP address for AnyCompany’s website, 192.0.2.0.

### ** Amazon Route 53**

==[**Amazon Route 53**](https://aws.amazon.com/route53) is a DNS web service.== It gives developers and businesses a reliable way to route end users to internet applications hosted in AWS. 

Amazon Route 53 connects user requests to infrastructure running in AWS (such as Amazon EC2 instances and load balancers). It can route users to infrastructure outside of AWS.

Another feature of Route 53 is **the ability to manage the DNS records for domain names.** You can **register new domain names directly in Route 5**3. You can **also transfer DNS records for existing domain names managed by other domain registrars**. This <u>enables you to manage all of your domain names within a single location</u>.

In the previous module, you learned about **Amazon CloudFront, a content delivery service.** The following example describes how <u>Route 53 and Amazon CloudFront work together to deliver content to customers</u>.

### **Example: How Amazon Route 53 and Amazon CloudFront deliver content**

![Architecture diagram of Amazon Route 53 and Amazon CloudFront working together to deliver content from Amazon EC2 instances](Module%204%20-%20Networking.assets/mR1nvYoC4OSUVg9a_WE71CA369xcdceJ2.png)

Suppose that AnyCompany’s application is running on several Amazon EC2 instances. These instances are in an Auto Scaling group that attaches to an Application Load Balancer. 

- 1

  1

  A customer requests data from the application by going to AnyCompany’s website. 

- 2

  2

  Amazon Route 53 uses DNS resolution to identify AnyCompany.com’s corresponding IP address, 192.0.2.0. This information is sent back to the customer. 

- 3

  3

  The customer’s request is sent to the nearest edge location through Amazon CloudFront. 

- 4

  4

  Amazon CloudFront connects to the Application Load Balancer, which sends the incoming packet to an Amazon EC2 instance.

## In Module 4, you learned about the following concepts:

- Structuring and connecting to a VPC
- Securing VPC resources with network access control lists and security groups
- Using Amazon Route 53 and Amazon CloudFront to deliver content

Who should be allowed to communicate with each other? - Then you can set up your network on AWS



Networking used to be the exclusive domain of topological geniuses. With AWS, networking is now simplified and abstracted to answer the simple question of who should be allowed to communicate with each other. As long as you can answer that question, then you can set up your network on AWS. 



We covered the basics of **VPC**, the <u>virtual private cloud</u>, the way that you isolate your workload in AWS, the **fundamentals of network security**, including <u>gateways, network ACLs, and security groups,</u> all methods that allow your security engineers to craft a network that allows healthy traffic access while dropping subversive attacks before they reach your instance, **ways to connect to AWS through VPN and even Direct Connect**, <u>secure pipelines that are either encrypted over the general internet</u> or <u>exclusive fiber used by you and you alone</u>. 



We also talked about the **global networks that AWS provides** using our <u>Edge locations</u>, how you can use <u>Route 53</u> for DNS, and how to use <u>CloudFront to cache content closer to your actual consumers</u>. 



So while this only scratches the surface of the many things you can do with AWS networking, we hope that it gives you an understanding of the key moving pieces you need to get your business started.

## ** Additional resources**

To learn more about the concepts that were explored in Module 4, review these resources.

- [ ] [Networking and Content Delivery on AWS](https://aws.amazon.com/products/networking)
- [ ] [AWS Networking & Content Delivery Blog](https://aws.amazon.com/blogs/networking-and-content-delivery/)
- [ ] [Amazon Virtual Private Cloud](https://aws.amazon.com/vpc)
- [ ] [What is Amazon VPC?](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [ ] [How Amazon VPC works](https://docs.aws.amazon.com/vpc/latest/userguide/how-it-works.html)

### Quiz

<u>**Your company has an application that uses Amazon EC2 instances to run the customer-facing website and Amazon RDS database instances to store customers’ personal information. How should the developer configure the VPC according to best practices?**</u>

The correct response option is **Place the Amazon EC2 instances in a public subnet and the Amazon RDS databases instances in a private subnet**.

 

A **subnet** is a section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private.

 

Public subnets contain resources that need to be accessible by the public, such as an online store’s website.

 

Private subnets contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories.



**Learn more:**

- [Amazon VPC](https://aws.amazon.com/vpc)
- [VPCs and subnets](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Subnets.html)



The correct response option is **AWS Direct Connect**.





 <u>**Which component or service can be used to establish a private dedicated connection between your company’s data center and AWS?**</u>

The other response options are incorrect because:

- A private subnet is a section of a VPC in which you can group resources that should be accessed only through your private network. Although it is private, it is not used for establishing a connection between a data center and AWS.
- DNS stands for Domain Name System, which is a directory used for matching domain names to IP addresses.
- Amazon CloudFront is a content delivery service. You can use CloudFront to store cached copies of your content at edge locations that are close to your customers.

**Learn more:**

- [AWS Direct Connect](https://aws.amazon.com/directconnect)



**<u>Which statement best describes security groups?</u>**

The correct response option is **Security groups are stateful and deny all inbound traffic by default**.



Security groups are stateful. This means that they use previous traffic patterns and flows when evaluating new requests for an instance.



By default, security groups deny all inbound traffic, but you can add custom rules to fit your operational and security needs.



**Learn more:**

- [Security groups for your VPC](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)

**<u>Which component is used to connect a VPC to the internet?</u>**

The correct response option is **I****nternet gateway.**


 The other response options are incorrect because:

- A public subnet is a section of a VPC that contains public-facing resources.
- An edge location is a site that Amazon CloudFront uses to store cached copies of your content for faster delivery to customers.
- A security group is a virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance.

**Learn more:**

- [Internet gateways](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Internet_Gateway.html)

---

**<u>Which service is used to manage the DNS records for domain names?</u>**

The correct response option is **Amazon Route 53**.

 

Amazon Route 53 is a DNS web service. It gives developers and businesses a reliable way to route end users to internet applications that host in AWS.

Another feature of Route 53 is the ability to manage the DNS records for domain names. You can transfer DNS records for existing domain names managed by other domain registrars. You can also register new domain names directly in Route 53.

The other response options are incorrect because:

- Amazon Virtual Private Cloud (Amazon VPC) is a service that enables you to provision an isolated section of the AWS Cloud. In this isolated section, you can launch resources in a virtual network that you define.
- AWS Direct Connect is a service that enables you to establish a dedicated private connection between your data center and VPC.  
- Amazon CloudFront is a content delivery service. It uses a network of edge locations to cache content and deliver content to customers all over the world.

**Learn more:**

- [Amazon Route 53](https://aws.amazon.com/route53)