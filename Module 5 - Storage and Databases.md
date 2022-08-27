5/11/22

# Module 5 - Storage and Databases

## **Learning objectives**

In this module, you will learn how to:

- Summarize the <u>basic concept of storage and databases</u>.
- Describe the benefits of <u>Amazon Elastic Block Store (Amazon EBS)</u>.
- Describe the benefits of <u>Amazon Simple Storage Service (Amazon S3)</u>.
- Describe the benefits of <u>Amazon Elastic File System (Amazon EFS)</u>.
- Summarize <u>various storage solutions</u>.
- Describe the benefits of <u>Amazon Relational Database Service (Amazon RDS)</u>.
- Describe the benefits of <u>Amazon DynamoDB</u>.
- Summarize <u>various database services.</u>

**Elastic, scalable, disaster-resistant, cost optimized architecture that now has a global highly secured network that can be deployed entiredly programatically.** 

Databases and storage - choose right database for desk and right storage for the data type

## Instance stores and Amazon Elastic Block Store (Amazon EBS)

Applications need access to CPU, memory , network, and storage

- EC2 gives you access to all of these

Applications often need access to block-level storage. 

- When a file is updated, the whole series of blocks are not overwritten, only the pieces that change get updated

- This makes it an efficient storage type  when working with databases, enterprise software, and file systems

  ![image-20220512124428495](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512124428495.png)

**EC2 instances have harddrives as well:** 

- ==Instance Store Volumes== - these volumes are physically attached to the hosts your instance are running on top of, and you can write to it like a normal hard drive 

  - catch: since it is physically attached to host, if you turn off the EC2 instance, all data written to the instance store volume will be deleted

  ![image-20220512124601022](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512124601022.png)

The reason for this is that if you stop the instance, it is likely it will start up on another host, a host where the volume does not exist (**remember EC2 instances are virtual machines**)

![image-20220512125226377](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512125226377.png)

Bc of this temporary nature, they are useful in situations where you can lose the data being written to the drive, such as temporary files, scratch data, and data that can be easily recreated without consequence.

- i.e., do not write important data to the EC2 drives that come up with EC2 instances 

**You'll need data that persists outside of the EC2 instance** 

- You don't want your database getting deleted everytime you stop an EC2 instance

  ![image-20220512125609787](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512125609787.png)

  - This is where  ==Amazon Elastic Block Store (Amazon EBS)== comes into play

    - With EBS, you can create virtual hard drives, that we call ==EBS volumes== that you can attach to your EC2 instances

      - different from your local instance store volumes and they aren't directly tied to the host that your EC2 is running on.

      - This means that the data you write to an EBS volume can persist between start and stop of an instance

        ![image-20220512130135043](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512130135043.png)

  **EBS Volumes come in different sizes and types:** 

  ![image-20220512130210171](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512130210171.png)

- You define size, type and configurations of volume you need. 
  - Provision volume and attach it to your EC2 instance, from there you can configure your application to write to the volume and you're good to go. 
  - If you stop and start EC2 instance, the data remains

==Use case for EBS volumes is to have a harddrive that is persistent that your applications can write to.==

- <u>EBS allows you to take incremental backups of your data called ==snapshots==</u>
- important you take regular snapshots of your EBS volume
- This way if your drive becomes corrupted, you haven't lost your data, and you can restore that data from a snapshot

### **Instance stores**

Block-level storage volumes behave like physical hard drives.

==An [**instance store**](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html) provides temporary block-level storage for an Amazon EC2 instance.== An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance. When the instance is terminated, you lose any data in the instance store.

<u>Amazon EC2 instances are virtual servers. If you start an instance from a stopped state, the instance might start on another host, where the previously used instance store volume does not exist</u>. Therefore, AWS recommends instance stores for use cases that involve temporary data that you do not need in the long term.

![When an Amazon EC2 instance is terminated, all data on the attached EBS volume remains available.](Module%205%20-%20Storage%20and%20Databases.assets/FsqE_uY1Kh44ZQYQ_ym_B26HbnRb-vq3N.png)

==[**Amazon Elastic Block Store (Amazon EBS)**](https://aws.amazon.com/ebs) is a service that provides block-level storage volumes that you can use with Amazon EC2 instances.== If you stop or terminate an Amazon EC2 instance, <u>all the data on the attached EBS volume remains available</u>.

<u>To create an **EBS volume**, you define the configuration</u> (such as volume size and type) and provision it. <u>After you create an EBS volume, it can attach to an Amazon EC2 instance</u>.

Because EBS volumes are for data that needs to persist, it’s important to back up the data. You can <u>take incremental backups of EBS volumes by creating **Amazon EBS snapshots**</u>.

### **Amazon EBS snapshots**

![image-20220512131620401](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512131620401.png)

==An [**EBS snapshot**](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html) is an incremental backup.== This means that <u>the first backup taken of a volume copies all the data</u>. For subsequent backups, <u>only the blocks of data that have changed since the most recent snapshot are saved.</u> 

<u>Incremental backups are different from full backups</u>, in which all the data in a storage volume copies each time a backup occurs. The full backup includes data that has not changed since the most recent backup.

---

## Amazon Simple Storage Service (Amazon S3)

Amazon Simple Storage Service - receipts, excel spread sheets, text files, etc

![image-20220512132151462](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512132151462.png)

- **allows you to store and retrieve an unlimited amount of data at any scale** 
- Instead of storing them in a file directory, you store them in what we call <u>buckets</u> 
- <u>maximum size you can upload is 5tb</u>
- you can also <u>version objects</u> to protect them from accidental deletion of an object
- You can even <u>create multiple buckets</u> and <u>store them across different classes or tiers of data</u>. You can then c<u>reate permissions</u> to limit who can see or even access objects. And <u>you can even stage data between different tiers</u> 
  - these tiers offers mechanisms for different storage use cases such as data that needs to be accessed frequently vs audit data that needs to be retained for several years



1. ==**Amazon S3 Standard**== - It comes with 11 9s of durability, i.e.e 99.99999999999 % probability that it will retain intact after one year. 

   - furthermore, data is stored in such a way that AWS can sustain the concurrent loss of data in 2 seperate storage facilities 
     - this is bc data is stored in at at least 3 different facilities, so multiple copies reside across locations
   - Useful way to use S3 is static website hosting (collection of html files - and each page is akin to a physical page on the site)
     - you can do this by uploading all your html files and static assets, and checking a box to host it as a static website (instant website)
     - You can still have animations and moving parts to your website

2. ==**Amazon S3 Standard-Infrequent Access (S3 Standard-IA or S3-IA)**== - used for data that is accessed less frequently, but requires rapid access when needed

   - it's a perfect place to store backups, disaster recovery files, or any object that requires a long-term storage

3. **==Amazon S3 Glacier==**

   ![image-20220512133202629](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512133202629.png)

   - for <u>saving auditing data that doesn't need to be retrieved rapidly,</u> <u>you can use Amazon S3 Glacier to archive that data</u>
   - To use Glacier, you can simply move data to it or you can create vaults and populate them with archives
   - And if <u>you have compliance requirements around retaining data for, say, a certain period of time</u>, <u>you can employ an S3 Glacier vault lock policy and lock your vault</u>. 
     - You can specify controls such as <u>Write Once/ Read Many (WORM)</u> in a vault policy and lock the policy from future edits
       - Once locked the policy can no longer be changed 
   - You also have 3 options for retrieval which range from minutes to hours
   - And <u>you have the option of uploading directly to Glacier</u> or <u>using S3 Lifecycle policies</u>
     - **==<u>Amazon S3 Lifecycle management:</u> Move data automatically between tiers==**
       - With Lifecycle policies you can create policies without changing application code and it will peform those moves for your automatically
       - Another example of a managed AWS service that takes a load off you, so you can manage your other business needs

4. Just to note that there are other storage classes. Like ==**S3 Infrequent Access One Zone**== and  **==S3 Glacier Deep Archive==** that you can use. Happy storing.

### Object Storage

![image-20220512135307853](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512135307853.png)

==In **object storage**, each object consists of data, metadata, and a key.==

The **data** might be an <u>image, video, text document, or any other type of file</u>. **Metadata** contains information about <u>what the data is, how it is used, the object size,</u> and so on. An object’s **key** is its <u>unique identifier</u>.

**Recall that when you modify a file in block storage, only the pieces that are changed are updated.** <u>When a file in object storage is modified, the entire object is updated.</u>

### **Amazon Simple Storage Service (Amazon S3)**

==[**Amazon Simple Storage Service (Amazon S3)**](https://aws.amazon.com/s3/) is a service that provides object-level storage.== Amazon S3 stores data as objects in buckets.

You can upload any type of file to Amazon S3, such as images, videos, text files, and so on. For example, <u>you might use Amazon S3 to store backup files, media files for a website, or archived document</u>s. Amazon S3 offers <u>unlimited storage space</u>. The <u>maximum file size for an object in Amazon S3 is 5 TB</u>.

When you upload a file to Amazon S3, you can set <u>permissions to control visibility and access to it</u>. You can also use the Amazon S3 <u>versioning feature to track changes to your objects over time</u>.

### **Amazon S3 storage classes**

With Amazon S3, you pay only for what you use. You can choose from [a range of storage classes](https://aws.amazon.com/s3/storage-classes) to select a fit for your business and cost needs. When selecting an Amazon S3 storage class, consider these two factors:

- <u>How often</u> you plan to retrieve your data
- How available you need your data to be

To learn more about the Amazon S3 storage classes, select the **+** symbol next to each category.

**==S3 Standard==**

–

- <u>Designed for frequently accessed data</u>
- Stores data in a minimum of three Availability Zones

S3 Standard provides high availability for objects. This makes it a good choice for a wide range of use cases, such as <u>websites, content distribution, and data analytics</u>. <u>S3 Standard has a higher cost than other storage classes intended for infrequently accessed data and archival storage</u>.

==**S3 Standard-Infrequent Access (S3 Standard-IA)**==

–

- <u>Ideal for infrequently accessed data</u>
- Similar to S3 Standard but has a lower storage price and higher retrieval price

S3 Standard-IA is ideal for <u>data infrequently accessed but requires high availability when needed</u>. Both S3 Standard and S3 Standard-IA <u>store data in a minimum of three Availability Zones</u>. S3 Standard-IA provides the same level of availability as S3 Standard but with a lower storage price and a higher retrieval price.

==**S3 One Zone-Infrequent Access (S3 One Zone-IA)**==

–

- Stores data in a <u>single Availability Zone</u>
- Has a lower storage price than S3 Standard-IA

Compared to S3 Standard and S3 Standard-IA, which store data in a minimum of three Availability Zones, S3 One Zone-IA stores data <u>in a single Availability Zone.</u> This makes it a good storage class to consider if the following conditions apply:

- You want to save costs on storage.
- You <u>can easily reproduce your data in the event of an Availability Zone failure</u>.

==**S3 Intelligent-Tiering**==

–

- <u>Ideal for data with unknown or changing access patterns</u>
- Requires a small monthly monitoring and automation fee per object

In the S3 Intelligent-Tiering storage class, <u>Amazon S3 monitors objects’ access patterns.</u> I<u>f you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, S3 Standard-IA</u>. I<u>f you access an object in the infrequent access tier, Amazon S3 automatically moves it to the frequent access tier, S3 Standard</u>.

==**S3 Glacier**==

–

- <u>Low-cost storage designed for data archiving</u>
- Able to retrieve objects within a few minutes to hours

**S3 Glacier is a low-cost storage class that is ideal for data archiving.** For example, you might use this storage class to store archived customer records or older photos and video files.

==**S3 Glacier Deep Archive**==

–

- <u>Lowest-cost object storage class ideal for archiving</u>
- Able to retrieve objects within 12 hours

When deciding between Amazon S3 Glacier and Amazon S3 Glacier Deep Archive, consider how quickly you need to retrieve archived objects. You can retrieve objects stored in the S3 Glacier storage class within a few minutes to a few hours. By comparison, you can retrieve objects stored in the S3 Glacier Deep Archive storage class within 12 hours.

---

**<u>You want to store data that is infrequently accessed but must be immediately available when needed. Which Amazon S3 storage class should you use?</u>**

The correct response option is **S3 Standard-IA**.

 

The S3 Standard-IA storage class is ideal for data that is infrequently accessed but requires high availability when needed. Both S3 Standard and S3 Standard-IA store data in a minimum of three Availability Zones. S3 Standard-IA provides the same level of availability as S3 Standard but at a lower storage price.

 

The other response options are incorrect because:

- In the S3 Intelligent-Tiering storage class, Amazon S3 monitors objects’ access patterns. If you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, S3 Standard-IA. If you access an object in the infrequent access tier, Amazon S3 automatically moves it to the frequent access tier, S3 Standard.
- S3 Glacier and S3 Glacier Deep Archive are low-cost storage classes that are ideal for data archiving. They would not be the best choice for this scenario, which requires high availability. You can retrieve objects stored in the S3 Glacier storage class within a few minutes to a few hours. By comparison, you can retrieve objects stored in the S3 Glacier Deep Archive storage class within 12 hours.

---

### **Comparing Amazon EBS and Amazon S3**

![image-20220512141257113](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512141257113.png)

![image-20220512141333359](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512141333359.png)

Each boasts dynamically distributed design for different demands - which storage class will ultimately be victorious? 

- To understand who wins, you need to clarify a use case

- **Round 1:** Photo analysis website,that needs to compare to animal photos that needs to be used by 1000s of people at once, this is the perfect use case for s3

  ![image-20220512142449577](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512142449577.png)

  - regionally distributed - 11 9s of durability
  - Cost savings substantial over running the same load on EBS
  - with additional advantage of it being server less (no Amazon EC2 instances are needed)

- **Round 2:** You have an 80 gigabyte video file you are making edit corrections on , the best storage class here we need to understand the different beween **object storage** (treats any file as a complete discrete object - but anytime there is a change, you must reupload the entire file) and **block storage** (breaks those files down to small component parts - blocks. 

  - This means if you update only one part of the video file, the engine only updates the block where those bits live. If you are making a bunch of micro edits using EBS block storage is the perfect use case. If you used S3, everytime you save changes, the system has to upload all 80 gb every time. EBS clearly wins this round )
  - ==If you are using complete objects or only occasional changes, S3 is victorious. If you are doing complex read/ write/ change function, then EBS is your winner==. All depends on your individual workload

---

## **Amazon Elastic File System (Amazon EFS)**

![image-20220512143934014](Module%205%20-%20Storage%20and%20Databases.assets/image-20220512143934014.png)

==**Amazon Elastic File System (Amazon EFS) - a managed file system**==

It is extremely common for a business to have shared file system across applications

- example, multiple servers running analytics on large amounts of data being stored in a shared file system
  - this data traditionally has been stored on premises (you'd have to make sure storage you have can keep up with the  amount of data your are storing, make sure backups are taken and that the data is stored redundantly, as well as manage all the servers hosting that data. 
  - With AWS, you don't need to worry about hardware. 
  - With EFS you can keep existing file systems in place and let AWS do all the heavy lfiting of the scaling and replication. 
- ==**Amazon EFS**: Multiple instances can access the data in EFS at the same time==
  - It scales up and down as needed, without you needing to do anything
  - Amazon EBS allows you to store files that you can access from EC2 instances
    - **What's the difference?** 
      - **Amazon EBS** 
        - volumes attach to EC2 instances
        - And are an availability zone resource
        - Need to be in the same Availability Zone to attache the EC2 instances  
        - (save files, you can run a database on it, it's a harddrive)
        - Volumes do not automatically scale to give you more storage
      - **Amazon EFS**
        - can have <u>multiple instances reading and writing simultaneously</u> 
        - Not just a blank harddrive, but it is a <u>true Linux file system</u>
        - <u>a regional resource</u>, meaning any EC2 instance in the region can write to the EFS file system 
        - As you write more data to EFS, it <u>automatically scales</u>, no need to provision anymore volumes

### **File storage**

==In **file storage**, multiple clients (such as users, applications, servers, and so on) can access data that is stored in shared file folders.== In this approach, <u>a storage server uses block storage with a local file system to organize files</u>. <u>Clients access data through file paths.</u>

Compared to block storage and object storage, file storage is <u>ideal for use cases in which a large number of services and resources need to access the same data at the same time.</u>

==[**Amazon Elastic File System (Amazon EFS)**](https://aws.amazon.com/efs/) is a scalable file system used with AWS Cloud services and on-premises resources.== As you add and remove files, Amazon EFS grows and shrinks automatically. It can <u>scale on demand to petabytes without disrupting applications</u>. 

### **Comparing Amazon EBS and Amazon EFS**

An **Amazon EBS** volume stores data in a **single** Availability Zone. 

- To attach an Amazon EC2 instance to an EBS volume, both the Amazon EC2 instance and the EBS volume must reside within the same Availability Zone.

**Amazon EFS** is a regional service. It stores data in and across **multiple** Availability Zones.

- The duplicate storage enables you to access data concurrently from all the Availability Zones in the Region where a file system is located. Additionally, <u>on-premises servers can access Amazon EFS using AWS Direct Connect</u>.

## **Amazon Relational Database Service (Amazon RDS)**

If you'd like to maintain relationships btw various types of data, it's based to use a **relational database management system**. 

- ex. you want to offer a promotional discount on their next purchase and you need a way to keep track of this relationship somewhere, in

- ==relational database management system== - store data in a way that it relates to other data 

  ![image-20220513153440139](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513153440139.png)

  - Relate both tables by a common attribute

  - Most common way to query data is by writing queries in SQL

  - ==AWS supported databases: MySQL, PostgreSQL, Oracle, Microsoft SQL Server==

    - A **lift-and-shift migration** - to run your database on Amazon EC2
      - you have control over same variables: os, memory, cpu, storage capacity
      - quick entry to cloud and can be migrated using standard practices and something like database migration service

  - Another option is to use a more managed service: 

    ![image-20220513154005184](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513154005184.png)

    ==Amazon Relational Database Service (Amazon RDS)== - supports all the relational databases mentioned above, but this service comes with added benefits (automated patching, backups, redundancy, failover, disaster recovery, which you usually have to manage yourself: 

    ![image-20220513154101820](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513154101820.png)

    - To make it even easier, migrate or deploy to ==Amazon Aurora== most mangaged relational database option:</u>![image-20220513154150683](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513154150683.png)
      - it comes in <u>two forms: MySQL and PostgreSQL</u> 
      - <u>1/10th the cost</u> of commercial databases
      - <u>Data replication</u> - across facilities so you have 6 copies at any given time
      - You can also <u>deploy up to 15 read replicas</u> so you can offload your reads and scale performance
      - <u>Continuous backup</u> to Amazon S3 
      - <u>Point-in-time recovery</u>

### Relational Databases

In a **relational database**, data is stored in a way that relates it to other pieces of data. 

An example of a relational database might be the coffee shop’s inventory management system. Each record in the database would include data for a single item, such as product name, size, price, and so on.

<u>Relational databases use **structured query language (SQL)** to store and query data.</u> This approach allows data to be stored in an easily understandable, consistent, and scalable way. For example, the coffee shop owners can write a SQL query to identify all the customers whose most frequently purchased drink is a medium latte.

Example of data in a relational database:

| **ID** | **Product name**           | **Size** | Price |
| :----- | :------------------------- | :------- | :---- |
| 1      | Medium roast ground coffee | 12 oz.   | $5.30 |
| 2      | Dark roast ground coffee   | 20 oz.   | $9.27 |

### **Amazon Relational Database Service**

==[**Amazon Relational Database Service (Amazon RDS)**](https://aws.amazon.com/rds/) is a service that enables you to run relational databases in the AWS Cloud.==

Amazon RDS is a managed service that automates tasks such as <u>hardware provisioning, database setup, patching, and backups</u>. With these capabilities, you can spend less time completing administrative tasks and more time using data to innovate your applications. You can integrate Amazon RDS with other services to fulfill your business and operational needs, such as <u>using AWS Lambda to query your database from a serverless application</u>.

**Amazon RDS provides a number of different security options.** Many Amazon RDS database engines <u>offer encryption at rest</u> (protecting data while it is stored) and <u>encryption in transit</u> (protecting data while it is being sent and received).

### **Amazon RDS database engines**

==Amazon RDS is available on six database engines==, which <u>optimize for memory, performance, or input/output (I/O).</u> Supported database engines include:

- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

### Amazon Aurora

[**Amazon Aurora**](https://aws.amazon.com/rds/aurora/) is an enterprise-class relational database. It is compatible with MySQL and PostgreSQL relational databases. It is up to five times faster than standard MySQL databases and up to <u>three times faster than standard PostgreSQL databases</u>.

Amazon Aurora helps to <u>reduce your database costs by reducing unnecessary input/output (I/O) operations</u>, while ensuring that your database resources remain reliable and available. 

C<u>onsider Amazon Aurora if your workloads require high availability</u>. It <u>replicates six copies of your data across three Availability Zones</u> and <u>continuously backs up your data to Amazon S3</u>.

## Amazon DynamoDB

![image-20220513160446230](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513160446230.png)

==Amazon DynamoDB - serverless database== - you do not need to manage instances or underlying infrastructure powering it

- With DynamoDB you create tables:

  - table is a place where you can store and query data

  - data is organized into items, and items have attributes

    ![image-20220513160557326](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513160557326.png)

- Y**ou do not need to worry about system scaling up or down -** dynamoDB manages it for you

- **DynamoDB stores data redundantly across availability zones**  and mirrors data across multiple drives under the hood for you (makes burden of operating a highly available database much lower)

- **DynamoDB, aside from being massively scalable, is also highly performant**

  - has a millisecond response time 
  - ex. when you have applications with potentially millions of users, having reusable lightning fast response times is important

- **==DynamoDB doesn't use SQL, i.e. it's a non-relational database==**

  - relational databases require that you have a well defined schema in place, which you then use SQL to query database, 

    - this has been the standard, but can have scaling and performance issues when under stress
    - rigid schema also makes it so that you can not have any variation in the types of data that you store in a table. So it might not be the b<u>est fit for a data set that is a little less rigid and is being accessed at a very high rate</u>
    - this is where nonrelational database come in

  - Non-relational databases tend to have simple flexible schemas, not complex rigid schemas laying out tables that all relate to each other

    - You can add and remove attributes from the table at any time
    - not every item in table  has to have the same attributes (this is great for data that has various variations from item to item)
      - bc of this flexibility, you can not run SQL queries on it, instead you'd write SQL queries on a small subset of attributes that are designated as keys
      - bc of this, queries tend to be simple and tend to focus on collection of items from a single table, not queries that span multiple tables
      - this query pattern, along with other factors like how underlying system, is designed, allows DynamoDB to be very quick including response time and highly scalable

    ![image-20220513161737256](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513161737256.png)

    - ==For example, on Prime Day in 2019, across the 48 hours, there were 7.11 trillion calls to the Dynamo API, peeking at 45.4 million requests per second==. That's insanely scalable, all without underlying database management

### **Nonrelational databases**

==In a **nonrelational database**, you create tables. A table is a place where you can store and query data.==

Nonrelational databases are sometimes referred to as “NoSQL databases” because they use structures other than rows and columns to organize data. <u>**One type of structural approach for nonrelational databases is key-value pairs**.</u> <u>With key-value pairs, data is organized into items (keys), and items have attributes (values)</u>. You can think of attributes as being different features of your data.

**In a key-value database, you can add or remove attributes from items in the table at any time**. <u>Additionally, not every item in the table has to have the same attributes</u>. 

Example of data in a nonrelational database:

| **Key** | **Value**                                                    |
| :------ | :----------------------------------------------------------- |
| 1       | **Name**: John Doe**Address**: 123 Any Street **Favorite drink**: Medium latte |
| 2       | **Name**: Mary Major **Address**: 100 Main Street **Birthday**: July 5, 1994 |

### **Amazon DynamoDB**

==[**Amazon DynamoDB**](https://aws.amazon.com/dynamodb/) is a key-value database service. It delivers single-digit millisecond performance at any scale.==

To learn about features of DynamoDB, select each flashcard to flip it.

- **Serverless:** 

  - DynamoDB is serverless, which means that yo<u>u do not have to provision, patch, or manage servers</u>. 

    You also <u>do not have to install, maintain, or operate software</u>.

- **Automatic Scaling**:

  - <u>As the size of your database shrinks or grows, DynamoDB automatically scales to adjust for changes</u> in capacity while maintaining consistent performance. 

    This makes it a suitable choice for use cases that require high performance while scaling

### Amazon RDS vs Amazon DynamoDB

![image-20220513163556431](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513163556431.png)

![image-20220513163618090](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513163618090.png)

Relational Databases have been around forever

ex. sale supply management system you have to analyze for weak spots, Amazon RDS is the pick here, because it is built for business analytics (bc you need complex relational joins)

ex. anything else - bc a lot of what people end up putting in relational databases end up being lookup tables, ex. employee contact list - this is all single table territory (overhead of relational database creates overhead), this is where DynamoDB wins 

---

What are the scenarios in which you should use Amazon Relational Database Service (Amazon RDS)? (Select TWO.)

- Running a serverless database

  Correctly unchecked

- 

  Using SQL to organize data

  Correctly checked

- 

  Storing data in a key-value database

  Correctly unchecked

- 

  Scaling up to 10 trillion requests per day

  Correctly unchecked

- 

  Storing data in an Amazon Aurora database

  Correctly checked

SUBMIT

Correct

The two correct response options are:

- Using SQL to organize data
- Storing data in an Amazon Aurora database

The other three response options are scenarios in which you should use Amazon DynamoDB.

---

## Amazon Redshift

![image-20220513171230813](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513171230813.png)

We need databases that can handle 1000s of interactions per second.

Sometimes, we need to go past "what is happening now" to "what did happen"

- this requires something else

In order to handle the velocity of real time read/write functionality, most relational databases tend to function fabulously at certain capacities (how much content it actually stores)

The problem with historical analytics (ex. show me how production has improved since we started) is that data collection never stops. 

With modern telemetry and the explosion of IoT, the volume of data will overwhelm even the best traditional database

- not just the volume, but the variety of data can be a problem
  - ex. you want to run business intelligence projects against data coming from different data stores, like inventory, financial and retail sales system. A single query across multiple databases might sound nice, but traditional database don't handle them that easily
- Once data becomes too complex to handle with traditional relational databases, you've entered the world of **data warehouses**
  - data warehouses specifially built for this kind of data. you look at historical analytics as opposed to operational analysis
  - historical may be as soon as "show me last hour's sales numbers across all the stores"
    - <u>key thing is data is now set</u>
      - for example, "how many bags of coffee do we have now" <- this can be changing as we speak
      - <u>as long as buisness question is looking back,</u> then a data warehouse is the right solution for that line of business intelligence 
  - many data ware house solutions out there
    - beyond that there might be a lot of heavylifting, keeping warehouse tuned 

==**Amazon Redshift** - data warehousing as a service==

- <u>massively scalable</u>

- Redshift nodes in multiple petabyte sizes (1000^5) is very common

  - in cooperation, you can directly run a single SQL query under exabytes (1000^6) of unstructured data running in data lakes
  - Redshift uses a variety of techniques that allows you to achieve up to 10x higher performance than traditional data bases when it comes to these kinds of business intelligence workloads

  - **understand that when you need big data BI solutions, Redshift allows you get started with single API calls**

==[**Amazon Redshift**](https://aws.amazon.com/redshift) is a data warehousing service that you can use for big data analytics. It offers the ability to <u>collect data from many sources</u> and helps you to understand <u>relationships and trends across your data.</u>==

---

## **AWS Database Migration Service**

![image-20220513182450888](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182450888.png)

What happens if you have a database tha is on premises or it is already in the cloud? It is possible to still migrate

**AWS Database Migration Service** - helps migrate database in a secure and easy fashion

- you migrate data from a source and target database

![image-20220513182558139](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182558139.png)

- **Homogeneous Migration**:
  - ![image-20220513182642126](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182642126.png)
  - ![image-20220513182655561](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182655561.png)
  - ![image-20220513182712135](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182712135.png)

![image-20220513182738008](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182738008.png)

- ![image-20220513182758385](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182758385.png)
- ![image-20220513182808951](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182808951.png)

- **Heteogenous Migratrion** - 
  - 2 steps, 
    1. convert using the AWS Schema Conversion tool (converts schema and code )
    2. Use DMS to migrate data from source to target database
  - ![image-20220513182843106](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182843106.png)
  - ![image-20220513182900080](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513182900080.png)

![image-20220513183035837](Module%205%20-%20Storage%20and%20Databases.assets/image-20220513183035837.png)

Not the only use cases for DMS

- **development and test database migrations** - when you want developers to test against production data wihtout effecting production users
  - in this case you use DMS to migrate a copy of your production  production database to your test or dev env either once or continuously
- **database consolidation** - when you want to consolidate several databases into one central database
- **continuous database replication** - Sending ongoing copies of your data to other target sources instead of doing a one-time migration, i.e. when you use DMS to perform continuous data replication
  - this could be for disaster recovery or because of geographic seperation 

### **AWS Database Migration Service (AWS DMS)**

==[**AWS Database Migration Service (AWS DMS)**](https://aws.amazon.com/dms/) enables you to migrate relational databases, nonrelational databases, and other types of data stores==

**With AWS DMS, you move data between a source database and a target database. [The source and target databases](https://aws.amazon.com/dms/resources) can be of the same type or different types. During the migration, your source database remains operational, reducing downtime for any applications that rely on the database.** 

For example, suppose that you have a MySQL database that is stored on premises in an Amazon EC2 instance or in Amazon RDS. Consider the MySQL database to be your source database. Using AWS DMS, you could migrate your data to a target database, such as an Amazon Aurora database.

## Additional Databases

There is no one size fits all database for all purposes. 

### **Additional database services**

To learn more, select the **+** symbol next to each category.



–

[**Amazon DocumentDB**](https://aws.amazon.com/documentdb) is a document database service that supports MongoDB workloads. (MongoDB is a document database program.)

- Example use case: Great for content management, catalogues, user profiles

–

[**Amazon Neptune**](https://aws.amazon.com/neptune) is a graph database service. 

You can use Amazon Neptune to build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.

- Example use case:  Social network you need to track
  - engineered for social networks and recommendation engines, also great for fraud detection needs
  - or  you have a supply chain where you have to check that nothing is loss, banking records that require 100 % immutability (that's what block chain is all about)

–

[**Amazon Quantum Ledger Database (Amazon QLDB)**](https://aws.amazon.com/qldb) is a ledger database service. 

You can use Amazon QLDB to review a complete history of all the changes that have been made to your application data.

- immutable system of record where any entry can never be removed from the audits

–

[**Amazon Managed Blockchain**](https://aws.amazon.com/managed-blockchain) is a service that you can use to create and manage blockchain networks with open-source frameworks. 

Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.

- probably not what you really need, it solves part of the equation but has a decentralization component that's not what financial regulators want to see, what you really need is an immutable ledger

–

[**Amazon ElastiCache**](https://aws.amazon.com/elasticache) is a service that adds caching layers on top of your databases to help improve the read times of common requests. (from millseconds to microseconds)

It supports two types of data stores: Redis and Memcached.

- to make databases go faster

–

[**Amazon DynamoDB Accelerator (DAX)**](https://aws.amazon.com/dynamodb/dax/) is an in-memory cache for DynamoDB. 

It helps improve response times from single-digit milliseconds to microseconds.

native caching layer designed to dramatically improve read times for your non relational data 

---

## Module 5 summary

In Module 5, you learned about the following concepts:

- Amazon EC2 instance store and Amazon EBS
- Amazon S3 - store objects in AWS
- Amazon EFS  - file storage use cases
- Relational databases and Amazon RDS 
- Nonrelational databases and DynamoDB
- Amazon Redshift - data warehouse needs
- AWS DMS - migration
- Additional database services and accelerators



## Additional resources

To learn more about the concepts that were explored in Module 5, review these resources.

- [Cloud Storage on AWS](https://aws.amazon.com/products/storage)
- [AWS Storage Blog](https://aws.amazon.com/blogs/storage/)
- [Hands-On Tutorials: Storage](https://aws.amazon.com/getting-started/hands-on/?awsf.getting-started-category=category%23storage&awsf.getting-started-content-type=content-type%23hands-on)
- [AWS Customer Stories: Storage](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc|product%23api-gateway|product%23cloudfront|product%23route53|product%23directconnect|product%23elb&awsf.customer-references-category=category%23storage)
- [AWS Database Migration Service](https://aws.amazon.com/dms/)
- [Databases on AWS](https://aws.amazon.com/products/databases)
- [Category Deep Dive: Databases](https://aws.amazon.com/getting-started/deep-dive-databases/)
- [AWS Database Blog](https://aws.amazon.com/blogs/database/)
- [AWS Customer Stories: Databases](https://aws.amazon.com/solutions/case-studies/?customer-references-cards.sort-by=item.additionalFields.publishedDate&customer-references-cards.sort-order=desc&awsf.customer-references-location=*all&awsf.customer-references-segment=*all&awsf.customer-references-product=product%23vpc|product%23api-gateway|product%23cloudfront|product%23route53|product%23directconnect|product%23elb&awsf.customer-references-category=category%23databases)



## Module 5: Quiz

---

**<u>Which Amazon S3 storage classes are optimized for archival data? (Select TWO.)</u>**

The correct two response options are:

- **S3 Glacier**
- **S3 Glacier Deep Archive**

Objects stored in the S3 Glacier storage class can be retrieved within a few minutes to a few hours. By comparison, objects that are stored in the S3 Glacier Deep Archive storage class can be retrieved within 12 hours.

 

The other response options are incorrect because:

- S3 Standard is a storage class that is ideal for frequently accessed data, not archival data.
- S3 Intelligent-Tiering monitors access patterns of objects and automatically moves them between the S3 Standard and S3 Standard-IA storage classes. It is not designed for archival data.
- S3 Standard-IA is ideal for data that is infrequently accessed but requires high availability when needed.

---

<u>**Which statement or statements are TRUE about Amazon EBS volumes and Amazon EFS file systems?**</u>

Correct

The correct response option is: **EBS volumes store data within a single Availability Zone. Amazon EFS file systems store data across multiple Availability Zones**.

 

An EBS volume must be located in the same Availability Zone as the Amazon EC2 instance to which it is attached.

 

Data in an Amazon EFS file system can be accessed concurrently from all the Availability Zones in the Region where the file system is located.



**Learn more:**

- [Amazon EBS volumes](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volumes.html)
- [Amazon EFS: How it works](https://docs.aws.amazon.com/efs/latest/ug/how-it-works.html)
- 

---

**<u>You want to store data in an object storage service. Which AWS service is best for this type of storage?</u>**

The correct response option is **Amazon Simple Storage Service (Amazon S3**).

 

The other response options are incorrect because:

- Amazon Managed Blockchain is a service that you can use to create and manage blockchain networks with open-source frameworks. Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.
- Amazon Elastic File System (Amazon EFS) is a scalable file system used with AWS Cloud services and on-premises resources. It does not store data as object storage.
- Amazon Elastic Block Store (Amazon EBS) is a service that provides block-level storage volumes that you can use with Amazon EC2 instances.

---

**<u>Which statement best describes Amazon DynamoDB?</u>**

The correct response option is **A serverless key-value database service**.

 Amazon DynamoDB is a key-value database service. It is serverless, which means that you do not have to provision, patch, or manage servers. 

The other response options are incorrect because:

- A service that enables you to run relational databases in the AWS Cloud describes Amazon Relational Database Service (Amazon RDS).
- A service that you can use to migrate relational databases, nonrelational databases, and other types of data stores describes AWS Database Migration Service (AWS DMS).
- An enterprise-class relational database describes Amazon Aurora.

---

**<u>Which service is used to query and analyze data across a data warehouse?</u>**

The correct response option is **Amazon Redshift**.

 

Amazon Redshift is a data warehousing service that you can use for big data analytics. Use Amazon Redshift to collect data from many sources and help you understand relationships and trends across your data.

 

The other response options are incorrect because:

- Amazon Neptune is a graph database service. You can use Amazon Neptune to build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, and knowledge graphs.
- Amazon DocumentDB is a document database service that supports MongoDB workloads.
- Amazon ElastiCache is a service that adds caching layers on top of your databases to help improve the read times of common requests.

---

