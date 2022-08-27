# AWS Practice Questions 6/14/22

https://TutorialsDojo.com

1. ![image-20220614170425548](AWS%20Practice%20Questions%20061422.assets/image-20220614170425548.png)

---

2. ![Screen Shot 2022-06-14 at 5.05.08 PM](AWS%20Practice%20Questions%20061422.assets/Screen%20Shot%202022-06-14%20at%205.05.08%20PM.png)

![Screen Shot 2022-06-14 at 5.05.55 PM](AWS%20Practice%20Questions%20061422.assets/Screen%20Shot%202022-06-14%20at%205.05.55%20PM.png)

To access AWS CLI (Command Line Interface) ***programatically*** - you need an **access key**

---



5. ![image-20220614170859585](AWS%20Practice%20Questions%20061422.assets/image-20220614170859585.png)

![image-20220614170930780](AWS%20Practice%20Questions%20061422.assets/image-20220614170930780.png)

6. ![image-20220614171051453](AWS%20Practice%20Questions%20061422.assets/image-20220614171051453.png)

- if you kill EC2 instance, you lose all your data

7. ![image-20220614171226121](AWS%20Practice%20Questions%20061422.assets/image-20220614171226121.png)

8. ![image-20220614171317302](AWS%20Practice%20Questions%20061422.assets/image-20220614171317302.png)

- **AWS Cost Explorer** - is for use when you already have  AWS services 
  - *AWS Cost Explorer* has an easy-to-use interface that lets you visualize, understand, and manage your AWS cloud costs and usage over time.
- interestingly, could not find anything on Google about AWS Sales Representative, might be new? 

9. ![image-20220614171439742](AWS%20Practice%20Questions%20061422.assets/image-20220614171439742.png)

- Durability - mean you won't lose data during an outage, i.e. you'll be able to get back data when things come back online
- ==**Amazon S3 Standard**== - It comes with 11 9s of durability, i.e.e 99.99999999999 % probability that it will retain intact after one year. 

11. ![image-20220614171703444](AWS%20Practice%20Questions%20061422.assets/image-20220614171703444.png)

12. ![image-20220614171835035](AWS%20Practice%20Questions%20061422.assets/image-20220614171835035.png)

- multiple EC2 instances
- ELB does **not** automatically scaled your EC2 instances

13. ![image-20220614172047197](AWS%20Practice%20Questions%20061422.assets/image-20220614172047197.png)

![image-20220614172103559](AWS%20Practice%20Questions%20061422.assets/image-20220614172103559.png)

14. ![image-20220614172219521](AWS%20Practice%20Questions%20061422.assets/image-20220614172219521.png)

- put keys away for root account

15. ![image-20220614172350458](AWS%20Practice%20Questions%20061422.assets/image-20220614172350458.png)

- Trusted Advisor is all about making recommendations to you

![image-20220614172419374](AWS%20Practice%20Questions%20061422.assets/image-20220614172419374.png)

16. ![image-20220614172539033](AWS%20Practice%20Questions%20061422.assets/image-20220614172539033.png)

- Management Console - where you go to launch
- AWS CloudFormation - Infrastructure as Code

17. ![image-20220614172632445](AWS%20Practice%20Questions%20061422.assets/image-20220614172632445.png)

OLTP ( **Online Transaction Processing**) - is a type of data processing  that consists of executing a number of transactions occurring  concurrently—online banking, shopping, order entry, or sending text  messages, for example.

18. ![image-20220614172720601](AWS%20Practice%20Questions%20061422.assets/image-20220614172720601.png)

- all compliance information you want from amazon is on AWS Artifact

19. ![image-20220614172839685](AWS%20Practice%20Questions%20061422.assets/image-20220614172839685.png)

20. ![image-20220614172913214](AWS%20Practice%20Questions%20061422.assets/image-20220614172913214.png)

---

21. ![image-20220614173059220](AWS%20Practice%20Questions%20061422.assets/image-20220614173059220.png)

![Screen Shot 2022-06-14 at 5.31.27 PM](AWS%20Practice%20Questions%20061422.assets/Screen%20Shot%202022-06-14%20at%205.31.27%20PM.png)

- S3 - not quite so low latency
- EBS - file system for your EC2 instances
  - **Amazon Elastic Block Store** provides raw block-level storage that  can be attached to Amazon EC2 instances and is used by Amazon Relational Database Service.

---

22. ![image-20220614173204075](AWS%20Practice%20Questions%20061422.assets/image-20220614173204075.png)

---

23. - **If you want <u>customer</u> to fully manage and patch OS - EC2 provides that level of control**, the other listed services are managed by AWS

- “**Elastic Compute Cloud**”



![image-20220614183607349](AWS%20Practice%20Questions%20061422.assets/image-20220614183607349.png)

---

24. **If an organization wants to test on multiple devices:** 

![image-20220614184740195](AWS%20Practice%20Questions%20061422.assets/image-20220614184740195.png)



![image-20220614173402485](AWS%20Practice%20Questions%20061422.assets/image-20220614173402485.png)

---

25. ![image-20220614173507183](AWS%20Practice%20Questions%20061422.assets/image-20220614173507183.png)

- **CAPEX** - where you invest in (investing in a physical data center)
- **OPEX** - renting where you don't worry about any ownership information (paying as you go)
- ![image-20220614173543984](AWS%20Practice%20Questions%20061422.assets/image-20220614173543984.png)

26. ![image-20220614173616522](AWS%20Practice%20Questions%20061422.assets/image-20220614173616522.png)

![image-20220614173640177](AWS%20Practice%20Questions%20061422.assets/image-20220614173640177.png)

Application Layer - layer 7

27. ![image-20220614173725362](AWS%20Practice%20Questions%20061422.assets/image-20220614173725362.png)

- not reserved instance bc it's  1 or 3 years whereas this is 3 months
- if you can upgrade it, likely it's a convertible RI

28. ![image-20220614173824283](AWS%20Practice%20Questions%20061422.assets/image-20220614173824283.png)

29. ![image-20220614173915484](AWS%20Practice%20Questions%20061422.assets/image-20220614173915484.png)

- Export as a CSV file etc that you can load into database of your choice

30. ![image-20220614174102442](AWS%20Practice%20Questions%20061422.assets/image-20220614174102442.png)

- especially working in public sector, clients will often request that data can't leave the United States, etc, 'Will my data stay in the US'
- first one would be good if you were getting paid to do it
- ![image-20220614174206991](AWS%20Practice%20Questions%20061422.assets/image-20220614174206991.png)

31. ![image-20220614174519411](AWS%20Practice%20Questions%20061422.assets/image-20220614174519411.png)

![image-20220614174544661](AWS%20Practice%20Questions%20061422.assets/image-20220614174544661.png)

Basic < Developer < Business < Enterprise hiearchy helps me remember it more

32. ![image-20220614174752452](AWS%20Practice%20Questions%20061422.assets/image-20220614174752452.png)

![image-20220614174744503](AWS%20Practice%20Questions%20061422.assets/image-20220614174744503.png)

33. ![image-20220614174900179](AWS%20Practice%20Questions%20061422.assets/image-20220614174900179.png)


 **Amazon Lightsail** offers easy-to-use virtual private server  (VPS) instances, containers, storage, databases, and more at a  cost-effective monthly price.

Cloudtrail = kind of like papertrail 

auto scaling goes well with elastic load balancing

34. ![image-20220614175153905](AWS%20Practice%20Questions%20061422.assets/image-20220614175153905.png)

![image-20220614175202829](AWS%20Practice%20Questions%20061422.assets/image-20220614175202829.png)

**Beanstalk** - is a platform as a promise so will not help with on premises

35. ![image-20220614175301947](AWS%20Practice%20Questions%20061422.assets/image-20220614175301947.png)

36. ![image-20220614175442290](AWS%20Practice%20Questions%20061422.assets/image-20220614175442290.png)

- Cloud Endure - disaster recovery solution

37. ![image-20220614175658764](AWS%20Practice%20Questions%20061422.assets/image-20220614175658764.png)

Aurora - **<u>only</u>** supports mySQL and postgreSQL (both open-sourced!), it does not support Microsoft SQL (likely bc it's proprietary)

for lift and shift operation you woud use - Amazon EC2

![image-20220614175736363](AWS%20Practice%20Questions%20061422.assets/image-20220614175736363.png)

38. ![image-20220614175759345](AWS%20Practice%20Questions%20061422.assets/image-20220614175759345.png)

39. ![image-20220614175843597](AWS%20Practice%20Questions%20061422.assets/image-20220614175843597.png)

40. ![image-20220614175948645](AWS%20Practice%20Questions%20061422.assets/image-20220614175948645.png)

42. ![image-20220614180115262](AWS%20Practice%20Questions%20061422.assets/image-20220614180115262.png)

