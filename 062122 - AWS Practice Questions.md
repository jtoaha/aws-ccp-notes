# AWS Practice Questions 6/21/22



1. ![image-20220621171427156](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621171427156.png)



2. ![image-20220621171557347](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621171557347.png)



- Will need security group if you want anyone to access it
  - When you launch an instance, you can specify one or more security groups. **If you don't specify a security group, Amazon EC2 uses the default security group**. 
- Root volume - you need this

---



3. ![image-20220621171716973](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621171716973.png)

![image-20220621171741937](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621171741937.png)

---

4. ![image-20220621171823114](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621171823114.png)

![image-20220621171830344](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621171830344.png)

---

5. ![image-20220621171926847](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621171926847.png)

6. ![image-20220621172011184](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172011184.png)

---

7. ![image-20220621172114035](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172114035.png)

Key phrase: "<u>does not require provisioning, maintaining, and administering **servers** for **backend components**</u>"

-  EMR (Elastic Map Reduce) - builds out EC2 instances for you

  - Amazon EMR (previously called Amazon Elastic MapReduce) is **a managed cluster platform that simplifies running big data frameworks,  such as Apache Hadoop and Apache Spark , on AWS to process and analyze  vast amounts of data**.
  - **Amazon EMR Serverless is a serverless option in Amazon EMR** that makes it easy for data analysts and engineers to run open-source  big data analytics frameworks without configuring, managing, and scaling clusters or servers.
  - ==While there is a serverless option for EMR, has to do with processing data not servers==

- Interesting note:  is there a difference between: serverless vs fully managed, a quick search says they are very similar, but that serverless is goes further than managed

  - <u>**Amazon API Gateway** is a fully managed service that makes it easy for  developers to create, publish, maintain, monitor, and secure APIs at any scale.</u> APIs act as the "front door" for applications to access data,  business logic, or functionality from your backend services. Using API  Gateway, you can create RESTful APIs and WebSocket APIs that enable  real-time two-way communication applications. **API Gateway supports  containerized and serverless workloads, as well as web applications.**

  API Gateway handles all the tasks involved in accepting and  processing up to hundreds of thousands of concurrent API calls,  including traffic management, CORS support, authorization and access  control, throttling, monitoring, and API version management. <u>API Gateway has no minimum fees or startup costs.</u> You pay for the API calls you  receive and the amount of data transferred out and, with the API Gateway tiered pricing model, you can reduce your cost as your API usage  scales.

- ![image-20220621172127112](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172127112.png)

---

8. ![image-20220621172257286](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172257286.png)

![image-20220621172310573](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172310573.png)

---

9. ![image-20220621172348762](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172348762.png)

10. ![image-20220621172425588](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172425588.png)

![image-20220621172438492](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172438492.png)

---

11. ![Screen Shot 2022-06-21 at 5.25.56 PM](062122%20-%20AWS%20Practice%20Questions.assets/Screen%20Shot%202022-06-21%20at%205.25.56%20PM.png)

**This is all Layer 3  - Network Transfer Protocol**

Layer 7 would be Application layer



![image-20220621172619390](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172619390.png)

---

12. ![image-20220621172701133](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172701133.png)

---

13. ![image-20220621172847856](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172847856.png)

- Trusted Advisor -  would just tell how close you are getting to those limits

- ![image-20220621172914004](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621172914004.png)

  - ==T**here is a limit on the number of running On-Demand Instances per AWS account per Region.** On-Demand Instance  limits are managed in terms of the *number of virtual central processing units (vCPUs)* that your running On-Demand Instances are using, regardless  of the instance type.==

    ==Even though Amazon EC2 automatically increases your On-Demand Instance limits based on your usage,                **you can request a limit increase if necessary**. For example<u>, if you intend to launch  more instances than your</u> **<u>current limit</u>** allows, you can request a limit increase.==

    



14. ![image-20220621173038918](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173038918.png)

**VPC is a free resource**

**You can provision a single Elastic IP for free, more than 1 it will charge you**

---

15. ![image-20220621173137542](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173137542.png)

![image-20220621173151004](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173151004.png)

---



16. ![image-20220621173349136](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173349136.png)

![image-20220621173406131](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173406131.png)

ELB - will make sure it's highly available

AppStream -is deployment technology



---

![image-20220621173504021](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173504021.png)

![image-20220621173511467](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173511467.png)

==It's actually 6 pillars now - **Sustainability** is something new they added.== **CROPSS** acronym to remember

![image-20220621173525798](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173525798.png)

![image-20220621173716574](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173716574.png)

Direct Connect - it's expensive AND a physical connection

- **interestingly, the connection is NOT internet-based** rather it's network-based

![image-20220621173738389](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621173738389.png)

---

19. ![image-20220621174059464](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174059464.png)

convertible has less of a discount than a non-convertible!

![image-20220621174119591](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174119591.png)

----

20. ![image-20220621174154902](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174154902.png)

---

21. ![image-20220621174244260](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174244260.png)

----

22. ![image-20220621174327225](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174327225.png)

23. ![image-20220621174412561](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174412561.png)

---

24. ![image-20220621174559337](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174559337.png)

Intelligent-Tiering -  will not help with upload itself

CORS - is more security related across domains

The *BatchWriteItem* operation puts or deletes multiple items in one or more tables. This operation enables you to put or delete several items across multiple tables in a single call.

**Multipart upload API - allows you parallelize processes**

- ==*Multipart upload* allows you to *upload* a single object as a set of parts. Each part is a contiguous portion of the object's data.==
- **After all parts of  your object are uploaded, Amazon S3 then presents the data as a single  object. With this feature you can create parallel uploads, pause and  resume an object upload, and begin uploads before you know the total  object size**

![image-20220621174633215](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174633215.png)

----

![image-20220621174833265](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174833265.png)

CodeBuild - good for buliding code, but not for storage

CodeCommit- to put request out there

Code Deploy - deploys application

CodeStar - web-based development environment 



AWS CodeBuild is **a fully managed continuous integration service that compiles source code, runs tests, and produces software packages that are ready to deploy**. With CodeBuild, you don't need to provision, manage, and scale your own build servers.

==CodeCommit is **a secure, highly scalable, managed source control service that hosts private Git repositories**. CodeCommit eliminates the need for you to manage your own source  control system or worry about scaling its infrastructure. You can use  CodeCommit to store anything from code to binaries.==

**AWS *CodeDeploy* is a fully managed deployment service** that automates software deployments to a variety of compute services such as Amazon EC2, AWS Fargate,

AWS CodeStar enables you to quickly develop, build, and deploy  applications on AWS. AWS CodeStar provides a unified user interface,  enabling you to easily manage your software development activities in  one place. 



![image-20220621174839990](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621174839990.png)

-----

26. ![image-20220621175000935](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175000935.png)

![image-20220621175037007](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175037007.png)

----

27. ![image-20220621175202561](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175202561.png)

![image-20220621175216417](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175216417.png)

**NAT - if you want going out to the internet but not back in**

----



28. ![image-20220621175432976](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175432976.png)

![image-20220621175443725](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175443725.png)

---

26. ![image-20220621175605234](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175605234.png)

consulting - helps you with solutions

This is more focused on technologies

---

20. ![image-20220621175649736](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175649736.png)

---



![image-20220621175814960](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175814960.png)

---

![image-20220621175831412](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175831412.png)

---

32. ![image-20220621175903828](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175903828.png)

33. ![image-20220621175926829](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621175926829.png)

Security Group - is for actual EC2 instance level

---

34. ![image-20220621180046499](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621180046499.png)

---

35. ![image-20220621180200938](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621180200938.png)

![image-20220621180208926](062122%20-%20AWS%20Practice%20Questions.assets/image-20220621180208926.png)

