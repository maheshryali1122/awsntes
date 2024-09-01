what are storage types in AWS and EBS Volume Types Elastic file share, Fsx, s3
A) EBS(Amazon Elastic Block Store):
    * These are storage volumes that we can attach to Amazon EC2 instances. We can attach multiple EBS volumes to a single instance. The volume and instance must be in the same Availability Zone.
    * Amazon EBS provides the following volume types: General Purpose SSD (gp2 and gp3), Provisioned IOPS SSD (io1 and io2), Throughput Optimized HDD (st1), Cold HDD (sc1), and Magnetic (standard). 
   EFS(Elastic file system):
    * EFS is a fully managed, storage provided by AWS (Amazon Web Services) that can be accessed by multiple EC2 instances  concurrently. With Amazon EFS, we can easily store and access data from multiple Amazon EC2 instances simultaneously, making it ideal for applications that require shared access to files.
    * NFS(Network file share):
      Network File System is a networking protocol for distributed file system. A file system defines the way data in the form of files is stored and retrived from storage devices such as hard disk drives, solid state drive and tape drives. 
      NFS enables system administrators to share all or a portion of a file system on a networked server to make it accessible to remote computer users. Clients with Authorization to access the shared file system can mount NFS shares, also known as shared file systems. NFS uses Remote Procedure Calls (RPCs) to route requests between clients and servers.
   S3:
     *  Amazon Simple Storage Service (Amazon S3) is storage for the internet. We can use Amazon S3 to store and retrieve any amount of data at any time, from anywhere on the web.
     Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance.
     # Amazon S3 Storage Classes
## Amazon S3 Standard (S3 Standard):
  * Designed for frequently accessed data.
  * Offers high durability, availability, and performance.
  *  Pricing:
        1) Higher storage cost compared to infrequent access classes.
        2) Suitable for data that needs to be accessed frequently

## Amazon S3 Standard-Infrequent Access (S3 Standard-IA)
   * Designed for data that is accessed less frequently but requires rapid access when needed.
   * Pricing:
        1) Lower storage cost compared to S3 Standard.
        2) Retrieval costs apply when data is accessed.
## Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA)
   * Designed for infrequently accessed data that does not require multiple availability zone resilience.
   * Pricing:
      1) Lower storage cost compared to S3 Standard-IA.
      2) Lower availability since data is stored in a single availability zone
## Amazon S3 Intelligent-Tiering (S3 Intelligent-Tiering)
   * Automatically moves data between two access tiers (frequent and infrequent access) based on changing access patterns.
   * Pricing:
      1) Storage cost similar to S3 Standard for frequently accessed data and S3 Standard-IA for infrequently accessed data.

     Features:
       * S3 Lifecycle – Configure a lifecycle configuration to manage your objects and store them cost effectively throughout their lifecycle. You can transition objects to other S3 storage classes or expire objects that reach the end of their lifetimes.
       * S3 Object Lock – Prevent Amazon S3 objects from being deleted or overwritten for a fixed amount of time or indefinitely. You can use Object Lock to help meet regulatory requirements that require write-once-read-many (WORM) storage or to simply add another layer of protection against object changes and deletions.
       * S3 Replication – Replicate objects and their respective metadata and object tags to one or more destination buckets in the same or different AWS Regions for reduced latency, compliance, security, and other use cases.
       * S3 Batch Operations – Manage billions of objects at scale with a single S3 API request or a few clicks in the Amazon S3 console. You can use Batch Operations to perform operations such as Copy, Invoke AWS Lambda function, and Restore on millions or billions of objects.
   
Instance store volume
A) An instance store volume exists only during the lifetime of the instance to which it is attached. Provide temporary block-level storage for your EC2 instances. Instance store is ideal for temporary storage of information that changes frequently, such as buffers, caches, scratch data, and other temporary content.


Types of file systems and explain
A) xfs and ext4 are the file systems

what is meant by snapshots and ami
A)  we need to create a full backup of an EC2 instance with an Amazon Machine Image (AMI) or take a snapshot of an individual volume. AMIs to launch new instances with preconfigured software and data. You can create AMIs when you want to establish a baseline, which is a reusable configuration for launching more instances.When you create an AMI of an existing EC2 instance, a snapshot is taken for all the volumes that are attached to the instance.

Life cycle management for snapshots
A)  Amazon Data Lifecycle Manager to automate Amazon EBS snapshot lifecycles.

Is it possible to change the disk type from gp2 to gp3 for an attached volume.
A) Yes, it is possible to change the disk type from gp2 to gp3 for an attached volume in AWS. 
Select the volume you want to change from gp2 to gp3.
Click on the "Actions" dropdown menu and select "Modify Volume."
In the "Modify Volume" dialog box, change the "Volume Type" to gp3.

Is it possible to reduce the size of the disk
A) Reducing the size of an EBS volume directly is not supported by AWS. However, you can achieve a reduction in size by following these steps.
Select the volume you want to resize and click on the "Actions" dropdown menu.
Choose "Create Snapshot" and follow the prompts to create a snapshot of the volume.
ind the snapshot you created, select it, and click on the "Actions" dropdown menu.
Choose "Create Volume."
In the "Create Volume" dialog box, select a smaller size for the new volume.
Ensure the volume is in the same Availability Zone as your instance.


what is meant by acls and object ownership and public access to the bucket
A) Access control lists (ACLs) – Grant read and write permissions for individual buckets and objects to authorized users.Policies are a simplified and more flexible access control option. With bucket policies and access point policies, you can define rules that apply broadly across all requests to your Amazon S3 resources.
B) If acls are disabled means All the objects in this bucket can be owned by this account. Acess to the bucket and its objects is specified using only policies
C) Ia acls are enabled means All the objects in this bucket can be owned by other accounts. Access to the bucket and its objects is specified by using ACLS



what is meant by cdn and pointofpresence and what is cloudfront
A) CDN is content delivery network. It brings content closer to the user. To bring server closer to the user CDN deploys servers at hundreds of locations all over the world. These server locations are called point of presence. The server inside the pop is commonly called as edge servers. Having many pops all over the world ensures that every user can reach fast edge server close to them. with dns based routing each pop has its own ip address. when the user looks up the ip address for the CDN. DNS returns the ip address of the pop closest to them. with anycast all pops share the same ip address.  Each edge server acts as a reverse proxy with a huge content cache. Static contents are cached on the edge server in the content cache. If a piece of content in the cache it could be quickly returned to the user. since the edge server only asks for a copy of the static content from the origin server if it is not in the cache. This greatly reduces the load and bandwidth reuirements of the origin server cluster. A modern CDN can also transform static content into more optimized formats. For example it would minify javascript bundles on the fly or transform a image file from an old format to a modern one like webp or avif

Cloudfront:
It provides solution for CDN
Amazon CloudFront is a web service that speeds up distribution of your static and dynamic web content, such as .html, .css, .js, and image files, to your users. CloudFront delivers your content through a worldwide network of data centers called edge locations. When a user requests content that you're serving with CloudFront, the request is routed to the edge location that provides the lowest latency (time delay), so that content is delivered with the best possible performance.
creation of cloudfront:
create an static content in s3 and we need to block the public access and enable versioning
For static website to work after creation of bucket in properties we have static website hosting option is there we need to enable we need to have index.html in index document and error document and create. Make sure public access is blocked and upload the index.html page in the bucket. We have an url in website hosting.
create a distribution in cloudfront in origin domain in this all s3 buckets are shown select the bucket.we do have origin access we need to select the legacy access identities(use a cloudfront origin access identity to access the bucket) it is a virtual user that will access the bucket.create an new oai(origin access identity) in this we need to update the policies. default root object we need to specify default root object. it will directly access the home page in this i have mentioned index.html. web application firewall depending on reuirement enable or disable.After creating we will have distribution domain name. in s3 bucket policies are there in permissions bucket policies are there. If you want to delete this distribution and disable this and delete this.

what is best practice includes secure access permissions, Cross-Region Replication, and a functioning, regularly tested backup.
A) Amazon S3 security best practices:
   * Disable access control lists (ACLs)
   * Ensure that your Amazon S3 buckets use the correct policies and are not publicly accessible
   * Identify potential threats to your Amazon S3 buckets by using Amazon GuardDuty
   * Implement least privilege access
   * Use IAM roles for applications and AWS services that require Amazon S3 access
   Cross-Region Replication:
   * we can use replication to enable automatic, asynchronous copying of objects across Amazon S3 buckets. Buckets that are configured for object replication can be owned by the same AWS account or by different accounts. You can replicate objects to a single destination bucket or to multiple destination buckets. The destination buckets can be in different AWS Regions or within the same Region as the source bucket.
   There are two forms of live replication: Cross-Region Replication (CRR) and Single-Region Replication (SRR).
   * Cross-Region Replication (CRR) – You can use CRR to replicate objects across Amazon S3 buckets in different AWS Regions. 
   * Single-Region Replication (SRR) – You can use SRR to copy objects across Amazon S3 buckets in the same AWS Region
what is meant by versioning in s3 
A) versioning means keeping multiple variants of an object in the same bucket. we can use versioning to preserve, retrieve and restore every version of every object stored in amazon s3 bucket.
* s3://bucket-name/key-name url is like this in s3

How aws logs can be stored in s3?
A) * AWS CloudTrail logs provide a record of actions taken by a user, role, or an AWS service. To store CloudTrail logs in S3
   * VPC Flow Logs capture information about the IP traffic going to and from network interfaces in your VPC. To store these logs in S3
   * S3 Server Access Logs

what are aws cli commands in s3
what is life cycle rules in amazon s3
A) Lifecycle rules to define actions you want amazon s3 to take during an objects lifetime such as transtioning objects to another storage class, archieving them or deleting them after a specified period of time
what is AWS backup
A) Backup Vault: Storage for the backups
Protected Resources: Resources which are enabled for backups
Backup Plan: Schedules of when to take backups
Jobs: This job executes to create a backup into vault
External Resources: Taking backups from non AWS sources
Organizations: AWS Organization is collection of AWS accounts for central management
Audit Manager.

What is meant by backup vault?
A) Backup vaults are containers where the backups are stored. We will have one or multiple backup vaults where backups are stored


## Creation of efs volume for multiple instances step by step process.
* Create an vpc with two public subnets and create security groups and create an efs file system and select the two subnets that are in different availability zone. take two ec2 instances and install the necessary commands as follows.
$ sudo apt-get update
$ sudo apt-get -y install git binutils rustc cargo pkg-config libssl-dev
$ git clone https://github.com/aws/efs-utils
$ cd efs-utils
$ ./build-deb.sh
$ sudo apt-get -y install ./build/amazon-efs-utils*deb

* create an folder in both the ec2 and execute below command
"sudo mount -t efs -o tls fs-002d37e2407bffca4:/ folder"
* After that syncing can be happened in both the ec2 instances.
# https://github.com/aws/efs-utils?tab=readme-ov-file#on-other-linux-distributions