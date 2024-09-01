# VPC:
* we can  launch AWS resources in a logically isolated virtual network that you've defined.
* A Virtual Private Cloud (VPC) is a virtual network dedicated to  AWS account. It is logically isolated from other virtual networks in the AWS Cloud.
* We  have complete control over virtual networking environment, including the selection of IP address range, creation of subnets, and configuration of route tables and network gateways.

# SUBNET
* A Subnet is a range of IP addresses in  VPC. Subnets allow you to segment VPC's IP address range into smaller, more manageable sections.
Types of Subnets:
  * Public Subnets: These subnets have access to the internet, usually through an Internet Gateway (IGW).
  * Private Subnets: These subnets are isolated from the internet and typically have access only within the VPC. Resources in private subnets can access the internet through a NAT gateway or NAT instance.

# CLOUDFRONT
* Amazon CloudFront is a web service that speeds up distribution of your static and dynamic web content, such as .html, .css, .js, and image files, to your users. CloudFront delivers your content through a worldwide network of data centers called edge locations. When a user requests content that you're serving with CloudFront, the request is routed to the edge location that provides the lowest latency (time delay), so that content is delivered with the best possible performance.

# Amazon SQS (Simple Queue Service)
* Amazon SQS is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. SQS helps you to move data between distributed application components and to decouple sending and receiving components.

# AMAZON LIGHTSAIL
* Amazon Lightsail is the easiest way to get started with Amazon Web Services (AWS) for anyone who needs to build websites or web applications. It includes everything you need to launch your project quickly—instances (virtual private servers), container services, managed databases, content delivery network (CDN) distributions, load balancers, SSD-based block storage, static IP addresses, DNS management of registered domains, and resource snapshots (backups)—for a low, predictable monthly price.

# Amazon S3 (Simple Storage Service)
Amazon S3 (Simple Storage Service) is a scalable, high-speed, web-based cloud storage service designed for online backup and archiving of data and applications on Amazon Web Services (AWS). S3 provides a simple web services interface that can be used to store and retrieve any amount of data, at any time, from anywhere on the web.
# Difference between S3 and EBS:
Summary of Critical Differences:
Feature	        Amazon S3	                                Amazon EBS
Storage Type	Object Storage	                            Block Storage
Data Structure	Buckets and Objects	                        Volumes
Accessibility	Internet-Accessible	                        Instance-Accessible
Use Cases	Static content,backups,media storage	    Databases,boot volumes,transactional apps
Durability	99.999999999% (11 nines)	                   99.999%
Availability Multi-region and class-based availability	   Availability Zone-based redundancy
Performance	High throughput, higher latency	               Low latency,    consistent performance
Pricing Model  Pay-as-you-go(storage, transfer, requests) | Provisioned capacity (size and type)
# Amazon snowball:
* AWS Snowball is a service you can use to transfer large amounts of data between Amazon Simple Storage Service (Amazon S3) and your onsite data storage location at faster-than-internet speeds. Snowball supports two job types: import jobs and export jobs. Import jobs involve a data transfer from an on-premises source to an Amazon S3 bucket.
# Amazon snowmobile: 
* AWS Snowmobile is an exabyte-scale data transfer service used to move extremely large amounts of data to AWS. It involves physically transporting data using a secure, 45-foot long shipping container, hauled by a semi-trailer truck.


## Amazon AMI image:
    * There are many types of AMIs, but some of the common AMIs are:
      1) Fully backed ami
      2) Just Enough Baked AMI
      3) Hybrid AMI


*** We can have up to 200 Subnets per Amazon Virtual Private Cloud (VPC). ***

## Amazon RDS (Relational Database Service):

 * Amazon RDS is designed for relational database management. It is used for applications that require traditional relational database structures, such as transactional databases(A transactional database is a type of database designed to handle a large number of transactions performed by multiple users).
 * Supports multiple database engines: MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Amazon Aurora.
 * Manages routine database tasks such as backups, patching, and scaling.
 * Provides high availability and durability with Multi-AZ deployments.

## Amazon DynamoDB
 * Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability. It is designed for applications that require low latency at any scale.
 * NoSQL database supporting key-value and document data models

## Amazon Redshift
  * Amazon Redshift is a fully managed data warehouse service(A data warehouse service is a specialized type of database service designed to support the storage, retrieval, and analysis of large volumes of data from multiple sources. These services are optimized for complex queries and large-scale data processing tasks, typically used in business intelligence (BI) and data analytics applications.) that makes it simple and cost-effective to analyze all your data using SQL and existing Business Intelligence (BI) tools. It is designed for large-scale data warehousing and big data analytics.

## Recovery Time Objective (RTO)
  * RTO is the maximum acceptable amount of time that a system, application, or process can be down after a disaster or failure occurs. It indicates how quickly you need to restore your systems and services to avoid significant impact on your business.
  * If your RTO for a particular application is 2 hours, you must be able to recover and restore that application within 2 hours after a failure or disruption.

## Recovery Point Objective (RPO)
  * RPO is the maximum acceptable amount of data loss measured in time. It defines the point in time to which data must be restored to resume normal operations after a disaster. RPO indicates how much data loss your business can tolerate during a disruption.

## What is the difference between EBS and Instance Store?
  * EBS is a kind of permanent storage in which the data can be restored at a later point. When you save data in the EBS, it stays even after the lifetime of the EC2 instance. On the other hand, Instance Store is temporary storage that is physically attached to a host machine. With an Instance Store, you cannot detach one instance and attach it to another. Unlike in EBS, data in an Instance Store is lost if any instance is stopped or terminated.


*** Taking a backup of EFS. We can use the EFS-to-EFS backup solution to recover from unintended changes or deletion in Amazon EFS ***

*** AWS Ops Automator to handle all the snapshots automatically.This allows you to create, copy, and delete Amazon EBS snapshots ***

## Elastic Load Balancing (ELB):
   * AWS Elastic Load Balancing automatically distributes incoming application traffic across multiple targets. There are three main types of load balancers under ELB
   1) Application Load Balancer (ALB):
     * Layer: Operates at the application layer (Layer 7) of the OSI model.
     * Use Case: Ideal for HTTP and HTTPS traffic, providing advanced request routing targeted at the delivery of modern application architectures, including microservices and containers.
     * Supports path-based and host-based routing.
     Host bases routing:
       * https://aws.plainenglish.io/host-based-routing-in-aws-application-load-balancers-d0e7b1e793ac

   2) A Network Load Balancer (NLB) is designed to handle high volumes of traffic with low latency. It operates at the transport layer (Layer 4) of the OSI model, routing traffic based on IP protocol data.  

   3) A Classic Load Balancer (CLB) in AWS is a type of load balancer that operates at both the transport layer (Layer 4) and the application layer (Layer 7) of the OSI model. It distributes incoming application traffic across multiple EC2 instances in one or more Availability Zones, ensuring high availability and fault tolerance.

## Amazon CloudTrail:
  * AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account. With CloudTrail, you can log, continuously monitor, and retain account activity related to actions across your AWS infrastructure.   
  * CloudTrail records AWS API calls for your account and delivers log files to an Amazon S3 bucket.The recorded information includes the identity of the API caller, the time of the API call, the source IP address of the API caller, the request parameters, and the response elements returned by the AWS service.

## Latency Based Routing (LBR)
  * To route traffic to the endpoint that provides the lowest latency for the end user.

## Geolocation Routing (Geo DNS)
  * To route traffic based on the geographic location of the user making the DNS query.
## Hosted zone
  * A hosted zone is an Amazon Route 53 concept. A hosted zone is analogous to a traditional DNS zone file; it represents a collection of records that can be managed together, belonging to a single parent domain name. All resource record sets within a hosted zone must have the hosted zone's domain name as a suffix.

## AWS config:

AWS Config is a service that enables you to assess, audit, and evaluate the configurations of your AWS resources. It helps you track the configuration changes, maintain compliance with internal policies or regulatory standards, and troubleshoot operational issues

# Scenario Based Interview Questions on EC2, IAM and VPC


Q: You have been assigned to design a VPC architecture for a 2-tier application. The application needs to be highly available and scalable. 
   How would you design the VPC architecture?

A: In this scenario, I would design a VPC architecture in the following way.
   I would create 2 subnets: public and private. The public subnet would contain the load balancers and be accessible from the internet. The private subnet would host the application servers. 
   I would distribute the subnets across multiple Availability Zones for high availability. Additionally, I would configure auto scaling groups for the application servers.

Q: Your organization has a VPC with multiple subnets. You want to restrict outbound internet access for resources in one subnet, but allow outbound internet access for resources in another subnet. How would you achieve this?

A: To restrict outbound internet access for resources in one subnet, we can modify the route table associated with that subnet. In the route table, we can remove the default route (0.0.0.0/0) that points to an internet gateway. 
   This would prevent resources in that subnet from accessing the internet. For the subnet where outbound internet access is required, we can keep the default route pointing to the internet gateway.

Q: You have a VPC with a public subnet and a private subnet. Instances in the private subnet need to access the internet for software updates. How would you allow internet access for instances in the private subnet?

A: To allow internet access for instances in the private subnet, we can use a NAT Gateway or a NAT instance. 
   We would place the NAT Gateway/instance in the public subnet and configure the private subnet route table to send outbound traffic to the NAT Gateway/instance. This way, instances in the private subnet can access the internet through the NAT Gateway/instance.

Q: You have launched EC2 instances in your VPC, and you want them to communicate with each other using private IP addresses. What steps would you take to enable this communication?

A: By default, instances within the same VPC can communicate with each other using private IP addresses. 
  To ensure this communication, we need to make sure that the instances are launched in the same VPC and are placed in the same subnet or subnets that are connected through a peering connection or a VPC peering link. 
  Additionally, we should check the security groups associated with the instances to ensure that the necessary inbound and outbound rules are configured to allow communication between them.

Q: You want to implement strict network access control for your VPC resources. How would you achieve this?

A: To implement granular network access control for VPC resources, we can use Network Access Control Lists (ACLs). 
  NACLs are stateless and operate at the subnet level. We can define inbound and outbound rules in the NACLs to allow or deny traffic based on source and destination IP addresses, ports, and protocols. 
  By carefully configuring NACL rules, we can enforce fine-grained access control for traffic entering and leaving the subnets.

Q: Your organization requires an isolated environment within the VPC for running sensitive workloads. How would you set up this isolated environment?

A: To set up an isolated environment within the VPC, we can create a subnet with no internet gateway attached. 
   This subnet, known as an "isolated subnet," will not have direct internet connectivity. We can place the sensitive workloads in this subnet, ensuring that they are protected from inbound and outbound internet traffic. 
   However, if these workloads require outbound internet access, we can set up a NAT Gateway or NAT instance in a different subnet and configure the isolated subnet's route table to send outbound traffic through the NAT Gateway/instance.

Q: Your application needs to access AWS services, such as S3 securely within your VPC. How would you achieve this?

A: To securely access AWS services within the VPC, we can use VPC endpoints. VPC endpoints allow instances in the VPC to communicate with AWS services privately, without requiring internet gateways or NAT gateways. 
  We can create VPC endpoints for specific AWS services, such as S3 and DynamoDB, and associate them with the VPC. 
  This enables secure and efficient communication between the instances in the VPC and the AWS services.

Q: What is the difference between NACL and Security groups ? Explain with a use case ?

A: For example, I want to design a security architecture, I would use a combination of NACLs and security groups. At the subnet level, I would configure NACLs to enforce inbound and outbound traffic restrictions based on source and destination IP addresses, ports, and protocols. NACLs are stateless and can provide an additional layer of defense by filtering traffic at the subnet boundary.
  At the instance level, I would leverage security groups to control inbound and outbound traffic. Security groups are stateful and operate at the instance level. By carefully defining security group rules, I can allow or deny specific traffic to and from the instances based on the application's security requirements.
  By combining NACLs and security groups, I can achieve granular security controls at both the network and instance level, providing defense-in-depth for the sensitive application.

Q: What is the difference between IAM users, groups, roles and policies ?

A: IAM User: An IAM user is an identity within AWS that represents an individual or application needing access to AWS resources. IAM users have permanent long-term credentials, such as a username and password, or access keys (Access Key ID and Secret Access Key). IAM users can be assigned directly to IAM policies or added to IAM groups for easier management of permissions.
   IAM Role: An IAM role is similar to an IAM user but is not associated with a specific individual. Instead, it is assumed by entities such as IAM users, applications, or services to obtain temporary security credentials. IAM roles are useful when you want to grant permissions to entities that are external to your AWS account or when you want to delegate access to AWS resources across accounts. IAM roles have policies attached to them that define the permissions granted when the role is assumed.
   IAM Group: An IAM group is a collection of IAM users. By organizing IAM users into groups, you can manage permissions collectively. IAM groups make it easier to assign permissions to multiple users simultaneously. Users within an IAM group inherit the permissions assigned to that group. For example, you can create a "Developers" group and assign appropriate policies to grant permissions required for developers across your organization.
   IAM Policy: An IAM policy is a document that defines permissions and access controls in AWS. IAM policies can be attached to IAM users, IAM roles, and IAM groups to define what actions can be performed on which AWS resources. IAM policies use JSON (JavaScript Object Notation) syntax to specify the permissions and can be created and managed independently of the users, roles, or groups. IAM policies consist of statements that include the actions allowed or denied, the resources on which the actions can be performed, and any additional conditions.

Q: You have a private subnet in your VPC that contains a number of instances that should not have direct internet access. However, you still need to be able to securely access these instances for administrative purposes. How would you set up a bastion host to facilitate this access?

A: To securely access the instances in the private subnet, you can set up a bastion host (also known as a jump host or jump box). The bastion host acts as a secure entry point to your private subnet. Here's how you can set up a bastion host:
      Create a new EC2 instance in a public subnet, which will serve as the bastion host. Ensure that this instance has a public IP address or is associated with an Elastic IP address for persistent access.
      Configure the security group for the bastion host to allow inbound SSH (or RDP for Windows) traffic from your IP address or a restricted range of trusted IP addresses. This limits access to the bastion host to authorized administrators only.
      Place the instances in the private subnet and configure their security groups to allow inbound SSH (or RDP) traffic from the bastion host security group.
      SSH (or RDP) into the bastion host using your private key or password. From the bastion host, you can then SSH (or RDP) into the instances in the private subnet using their private IP addresses.


## https://github.com/iam-veeramalla/aws-devops-zero-to-hero/tree/main/interview-questions abhishek veeramalla aws interview questions

# AMAZON Inspector:
* Amazon Inspector is a security assessment service provided by AWS that helps improve the security and compliance of applications deployed on AWS. It automatically assesses applications for vulnerabilities or deviations from best practices.

# AWS storage gateway:
AWS Storage Gateway is a hybrid cloud storage service that enables on-premises applications to seamlessly use AWS cloud storage. It provides a way to integrate on-premises IT environments with cloud storage, facilitating data storage, backup, and disaster recovery. One of the configurations of AWS Storage Gateway is the File Gateway.
* File Gateway:
File Gateway provides a file interface to Amazon S3, making it easy to store and retrieve files as objects in S3 using the NFS (Network File System) and SMB (Server Message Block) protocols

# Advantage that users experience when they move on-premises workloads to the AWS Cloud
* Decrease the maintaining cost of datacenters

# AWS Service
* AWS Service Catalog is a service that allows organizations to create and manage catalogs of IT services that are approved for use on AWS. These IT services can include everything from virtual machine images, servers, software, and databases to complete multi-tier application architectures. AWS Service Catalog helps you centrally manage commonly deployed IT services, achieve consistent governance, and meet compliance requirements.

# AWS glue:
* AWS Glue is a fully managed extract, transform, and load (ETL) service provided by Amazon Web Services that makes it easy to prepare and transform data for analytics. It simplifies the process of moving data between data stores and enables data integration across multiple sources. AWS Glue provides a serverless environment, eliminating the need for provisioning and managing infrastructure.
# Amazon QuickSight
* Amazon QuickSight is a scalable, serverless, and embeddable business intelligence (BI) service provided by AWS. It allows you to create and publish interactive dashboards that include visualizations, graphs, and charts. QuickSight is designed to be fast, easy to use, and cost-effective, making it suitable for a wide range of users from data analysts to business executives.
# AWS Professional Services
* AWS Professional Services is a global team of experts that provides enterprise-level assistance to help organizations realize their desired outcomes with AWS. They collaborate with your team and partners to execute your cloud strategy, overcome challenges, and accelerate your adoption of AWS. The service is designed to help you achieve your business goals and optimize your AWS environment through best practices, methodologies, and tools.
# AWS Direct Connect
* AWS Direct Connect is a cloud service solution that enables you to establish a dedicated network connection between your on-premises infrastructure and AWS. This dedicated connection can reduce network costs, increase bandwidth throughput, and provide a more consistent network experience than Internet-based connections
# IAM Credential Report
* The IAM Credential Report in AWS is used to generate a comprehensive report of all IAM users and their associated credentials within your AWS account. This report helps you manage and audit IAM credentials and ensure security best practices

# Which AWS service or resource provides answers to the most frequently asked security-related questions that AWS receives from its users?
AWS Knowledge center

# AWS Artifact
* AWS Artifact is a service provided by Amazon Web Services (AWS) that offers on-demand access to AWS compliance reports and security and compliance documentation. It helps organizations understand and manage their compliance posture by providing access to various reports and certifications related to AWS services.
# Savings plans
* Savings Plans is a flexible pricing model offered by AWS that helps you save money on AWS EC2 instances and other AWS services compared to on-demand pricing. It provides cost savings in exchange for a commitment to use a specific amount of resources over a one- or three-year period

# AWS regions
* AWS Regions are geographical areas that contain multiple data centers, known as Availability Zones (AZs), designed to deliver high availability and fault tolerance for AWS services. Each AWS Region is a separate geographic area that operates independently of other regions, providing you with the ability to deploy applications and data in different parts of the world

# AWS Security Token Service
* AWS Security Token Service (STS) is a web service that provides temporary security credentials to users or applications for accessing AWS resources. It is used to grant access to AWS resources without needing to share long-term credentials, thus enhancing security and flexibility
# AWS Security Hub
* A cloud security posture management (CSPM) service that aggregates alerts from various AWS services and partner products in a standardized format
# Amazon macie
* Amazon Macie is a fully managed data security and privacy service that uses machine learning and pattern matching to help you discover, classify, and protect sensitive data stored in Amazon S3. It is designed to enhance data security, compliance, and privacy management by automating the detection and classification of sensitive information
# AWS Outposts
* AWS Outposts is a fully managed service that extends AWS infrastructure, services, and operations to on-premises environments. It brings the same AWS hardware, software, and services that you use in the cloud to your on-premises location, providing a consistent hybrid cloud experience
# Amazon WorkSpace
* Amazon WorkSpaces is a managed, secure desktop-as-a-service (DaaS) solution that allows you to provision virtual desktops for users in the cloud. It provides a scalable and cost-effective way to deliver desktop experiences without the need to manage physical hardware.

# Amazon AppStream 2.0
* Amazon AppStream 2.0 is a fully managed application streaming service that allows you to deliver desktop applications to users securely from the cloud. It enables users to access applications and data from any device without having to manage or maintain the underlying infrastructure

# Amazon Trusted advisor:
* Amazon Trusted Advisor is a service that provides real-time guidance to help you provision your AWS resources following best practices. It helps you optimize your AWS environment by offering recommendations to improve performance, security, cost management, and fault tolerance.


*** Amazon dynamodb is a key-value database that provides sub-millisecond latency on a large scale ***

# AWS Global Accelerator
* AWS Global Accelerator is a service that improves the availability and performance of your applications by directing traffic to the optimal AWS endpoint based on health, geography, and routing policies. It provides a global network infrastructure that accelerates the delivery of your applications and services to end users

# AWs S3 access analyzer
* Amazon S3 Access Analyzer is a tool that helps you identify and review the permissions associated with your Amazon S3 buckets and objects. It analyzes your S3 bucket policies, access control lists (ACLs), and access permissions to ensure that your data is securely configured and not unintentionally exposed.

# Amazon Redshift Serverless
* Amazon Redshift Serverless is a fully managed, on-demand cloud data warehousing service that enables you to run and scale data analytics workloads without having to manage the underlying infrastructure. It provides the capabilities of Amazon Redshift's data warehousing technology in a serverless model, allowing you to focus on querying and analyzing data without worrying about provisioning or managing clusters.

# Cool down period in autoscaling:
* In AWS Auto Scaling, the cooldown period is a setting that defines the amount of time to wait after a scaling activity completes before another scaling activity can start. This period allows time for newly launched instances to start up and begin handling traffic before another scaling activity begins, preventing unnecessary scaling actions.

# Cloudfront signed urls:
CloudFront signed URLs are URLs that grant access to private content for a limited time. These URLs contain cryptographic signatures created using a pair of public and private keys. The private key is used to sign the URL, and the corresponding public key, uploaded to CloudFront, is used to verify the signature.

# NAT instance:
A NAT (Network Address Translation) instance is an Amazon EC2 instance configured to provide network address translation services in a Virtual Private Cloud (VPC). It allows instances in a private subnet to access the internet while keeping those instances secure by not exposing them directly to the internet.

*** For an EC2 Instance to allow SSH, you can have the below configurations for the Security and Network ACL for Inbound and Outbound Traffic.The reason why Network ACL has to have both an Allow for Inbound and Outbound is because network ACLs are stateless. Responses to allowed inbound traffic are subject to the rules for outbound traffic (and vice versa). Whereas for Security groups, responses are stateful. So if an incoming request is granted, by default an outgoing request will also be granted.Options A and D are invalid because Security Groups are stateful. Here, any traffic allowed in the Inbound rule is allowed in the Outbound rule too. Option C is in. For more information on Network ACLs, please refer to the link below. https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_ACLs.html ***

# AWS VPC endpoint:
* A VPC endpoint enables you to privately connect your VPC to supported AWS services and VPC endpoint services powered by PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service. Traffic between your VPC and the other service does not leave the Amazon network. For more information on AWS VPC endpoints, please visit the following URL: https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-endpoints.html

# Server-side encryption
* Server-side encryption is about protecting data at rest. Using server-side encryption with customer-provided encryption keys (SSE-C) allows you to set your own encryption keys. With the encryption key you provide as part of your request, Amazon S3 manages both the encryption, as it writes to disks, and decryption, when you access your objects. Therefore, you don’t need to maintain any code to perform data encryption and decryption. The only thing you do is manage the encryption keys you provide.








