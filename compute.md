1) EC2 pricing model what is meant by spot ondemand and reserved instances
A) Ondemand:
     * With On-Demand Instances, you pay for computing capacity by the hour or second (with a minimum of 60 seconds) with no long-term commitment. You pay only for what you use, and the instance automatically scales up or down with changing workloads. 
   Reserved instances:
     * Reserved Instances provide a discounted rate and an optional capacity reservation for your instances. You rent the Reserved Instance for a fixed period at a lower per-second or per-hour rate than the equivalent On-Demand Instance. 
   Spot instances:
     *  These instances are often available at a significantly lower price compared to On-Demand Instances, making them a cost-effective option for many types of workloads

2) purpose based selections in ec2
A)  General Purpose:
     * General purpose instances provide a balance of compute, memory and networking resources, and can be used for a variety of diverse workloads. These instances are ideal for applications that use these resources in equal proportions such as web servers and code repositories
     eg: t2, t3, m4
    Compute optimized:
      * Compute Optimized instances are ideal for compute bound applications that benefit from high performance processors. Instances belonging to this category are well suited for batch processing workloads, media transcoding, high performance web servers, high performance computing (HPC), scientific modeling, dedicated gaming servers and ad server engines, machine learning inference and other compute intensive applications.
      eg: c4 and c5
    Memory optimized:
      * Memory optimized instances are designed to deliver fast performance for workloads that process large data sets in memory.
      eg: R4 and R5  

    Accelerated Computing
      * Accelerated computing instances use hardware accelerators, or co-processors, to perform functions, such as floating point number calculations, graphics processing, or data pattern matching, more efficiently than is possible in software running on CPUs. 
      eg: p4 and p5
    Storage Optimized:
      * Storage optimized instances are designed for workloads that require high, sequential read and write access to very large data sets on local storage. They are optimized to deliver tens of thousands of low-latency, random I/O operations per second (IOPS) to applications.
      eg: D2 and D3 

3) AWS EC2 instance Lifecycle and importance of hibernate
A) pending => running => stopping => stopped => shuttingdown => terminated

Instance Hibernate:
 * When you hibernate an instance, we signal the operating system to perform hibernation (suspend-to-disk), which saves the contents from the instance memory (RAM) to your Amazon EBS root volume. We persist the instance's Amazon EBS root volume and any attached Amazon EBS data volumes. When you start your instance, the Amazon EBS root volume is restored to its previous state and the RAM contents are reloaded. Previously attached data volumes are reattached and the instance retains its instance ID.

4) Types of auto scaling and instance refresh?
A) Auto scaling:
    * Amazon EC2 Auto Scaling helps you ensure that you have the correct number of Amazon EC2 instances available to handle the load for your application.  You can specify the minimum number of instances in each Auto Scaling group, and Amazon EC2 Auto Scaling ensures that your group never goes below this size. You can specify the maximum number of instances in each Auto Scaling group, and Amazon EC2 Auto Scaling ensures that your group never goes above this size. If you specify the desired capacity, either when you create the group or at any time thereafter, Amazon EC2 Auto Scaling ensures that your group has this many instances. If you specify scaling policies, then Amazon EC2 Auto Scaling can launch or terminate instances as demand on your application increases or decreases.
Health check grace period : The amount of time until ec2 auto scaling perfoms the first health check on new instances after they are put into service
 scaling policies: target scaling policies

5) What are the status checks in ec2
A) system status checks:
     * System status checks monitor the AWS systems on which your instance runs. These checks detect underlying problems with your instance that require AWS involvement to repair. When a system status check fails, you can choose to wait for AWS to fix the issue, or you can resolve it yourself.
     * The following are examples of problems that can cause system status checks to fail:
        a) Loss of network connectivity
        b) Loss of system power
        c) Hardware issues on the physical host that impact network reachability
   Instance status checks:
     *   Instance status checks monitor the software and network configuration of your individual instance. Amazon EC2 checks the health of the instance by sending an address resolution protocol (ARP) request to the network interface (NIC). These checks detect problems that require your involvement to repair. When an instance status check fails, you typically must address the problem yourself (for example, by rebooting the instance or by making instance configuration changes).

6) Launch template
A)  * A launch template is similar to a launch configuration, in that it specifies instance configuration information. It includes the ID of the Amazon Machine Image (AMI), the instance type, a key pair, security groups, and other parameters used to launch EC2 instances. However, defining a launch template instead of a launch configuration allows you to have multiple versions of a launch template.
    * With versioning of launch templates, you can create a subset of the full set of parameters. Then, you can reuse it to create other versions of the same launch template.

7) system manager
A) * Aws system manager gives you visibility and control of infrastructure on AWS
    a) It helps to manage EC2 and on-premise systems at scale
    b) It easily detect the problems
    c) Patching automation for enhanced compliance
    d) Integrated with cloud watch metrics.


8) osi model
A)

9) loadbalancers
A) Elastic Load Balancing (ELB):
   * AWS Elastic Load Balancing automatically distributes incoming application traffic across multiple targets. There are three main types of load balancers under ELB
   1) Application Load Balancer (ALB):
     * Layer: Operates at the application layer (Layer 7) of the OSI model.
     * Use Case: Ideal for HTTP and HTTPS traffic, providing advanced request routing targeted at the delivery of modern application architectures, including microservices and containers.
     * Supports path-based and host-based routing.
     Host bases routing:
       * https://aws.plainenglish.io/host-based-routing-in-aws-application-load-balancers-d0e7b1e793ac

   2) A Network Load Balancer (NLB) is designed to handle high volumes of traffic with low latency. It operates at the transport layer (Layer 4) of the OSI model, routing traffic based on IP protocol data.  

   3) A Classic Load Balancer (CLB) in AWS is a type of load balancer that operates at both the transport layer (Layer 4) and the application layer (Layer 7) of the OSI model. It distributes incoming application traffic across multiple EC2 instances in one or more Availability Zones, ensuring high availability and fault tolerance.

10) Route 53 active passive failover and latency based
A) Route 53:
   * Amazon Route 53 is a highly available and scalable Domain Name System (DNS) web service. Route 53 connects user requests to internet applications running on AWS or on-premises.
   Active-Passive Failover:
    * Active-passive failover routing is used to configure a primary (active) resource and a secondary (passive) resource. When the primary resource becomes unavailable, Route 53 automatically directs traffic to the secondary resource.

   Latency-Based Routing:
     * Latency-based routing directs traffic to the region with the lowest latency. This improves performance by sending users to the endpoint that provides the best response time.
11) What is meant by Elastic Network Interface?
A)  * Elastic Network Interface (ENI) is a virtual network interface that you can attach to an Amazon EC2 instance in a Virtual Private Cloud (VPC). It acts as a logical networking component in a VPC that represents a virtual network card.
   * Each ENI consists of a primary private IPv4 address, one or more secondary private IPv4 addresses, one Elastic IP address (IPv4) per private IPv4 address, one public IPv4 address, one or more IPv6 addresses, one or more security groups, a MAC address, and a source/destination check flag
12) what is meant by EC2?
A) Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers.