# Amazon EC2

- Is a web service that provides resizable compute capacity in the cloud 
- Reduces the time required to obtain and boot new server instances to minutes, 
- Allowing you to quickly scale capacity, both up and down, as your computing requiremtns change.

## Four different pricing models

- On Demand
  - Allows you to pay a fixed rate by the hour (or by the second) with no commitment
- Reserved
  - Provides you with a capacity reservation, and offer a significant discount  on the hourly charge for an instance.  Contract terms are 1 year or 3 year terms.
    - All Upfront
    - Partial Upfront
    - No Upfront
- Spot
  - Enables you to bid whatever price you want for instance capacity, providing for event greater savings if your app have flexible start and end times.
- Dedicated Hosts
  - Physical EC2 server dedicated for your use. Dedicated hosts can help you  reduce costs by allowing you to use your existing server-bound software licenses

### Spot instance

- If it is terminated by Amazon EC2, you will __NOT__ charged for a partial hour of usage
- else, If YOU terminate, you will be chaged for any hour in which the instance ran

## EC2 Instance Types - Mnemonic

- F For FPGA
- I For IOPS
- G Graphics
- H High Disk Throughput
- T Cheap general purpose (t2 micro)
- D For Density
- R For RAM
- M Main choice for general purpose apps
- C For Compute
- X Extreme memory
- Z Extreme memory and CPU
- A Arm-based workloads
- U Bare Metal

## EBS

- Termination Protection is __turned off__ by default, you must turn it on.
- On a EBS-Backed instance, the __default action is for the root EBS volume to be deleted__ when the instance is terminated
- EBS Root Volumes of your DEFAULT AML's __CAN__ be encrypted. You can also use a third party tool (such as bit locker etc) to encrypt the root volume, or this - can be done when creating AMI's (lab to follow) in the AWS console or using the API
- Additional volumes can be encrypted

## Security groups

- All Inbound traffic is blocked by default
- All Outbound traffic is allowed
- Changes to security groups take effect immediately
- You can have any number of EC2 instances within a security group
- You can have multiple security groups attached to EC2 instances
- Security groups are __STATEFUL__
- If you  create an inbound rule allowing traffic in, that traffic is automatically allowed back out again
- You cannot block specific IP addresses using SG, instead use __Network Access Control Lists__.
- You can specify allow rules, but not deny rules.

## Compare EBS Types

- Volumes exist on EBS. Think of EBS as a virtual hard disk
- Snapshots exist on S3. Think of snapshots as a photograph of the disk
- Snapshots are incremental

- If this is your first snapshot, it may take some time to create.
- To create a snapshots for Amazon EBS volumes that serve as root devices, you should stop the instance before taking the snapshot
- However you can take a snap while the instance is running
- You can create AMI's from both Volumes and Snapshots
- You can change EBS volume sizes on the fly, including changing the size and storage type
- Volumes will ALWAYS be in the same availability zone as the EC2 instance.

![SSD-HDD1](https://udemy-images.s3.amazonaws.com/redactor/raw/2019-01-19_22-34-15-d1fd30e8eaa8701ddd964e5878e78242.png)

![SSD-HDD1](https://udemy-images.s3.amazonaws.com/redactor/raw/2019-01-19_05-52-53-2f6fe79f1600d1f1c4eaab87872423d7.png)

## Migrating EBS

### Move EC2 volume

- In the same Region
  - Take a snapshot of it
  - Create an AMI from the snapshot
  - Use the AMI to launch the EC2 instance in a new AZ

- Other Regions
  - Take a snapshot of it
  - Create an AMI from the snapshot
  - Copy AMI from one region to the other
  - Use the Copied AMI to launch the new EC2 instance in the new region

## EBS encyption

- Snapshots of encrypted volumes are encrypted automatically
- Volumes restored from encrypted snapshots are encrypted automatically
- You can share snapshots, by only if they are unencrypted
- These snapshots can be shared with other AWS accounts or made public

## EBS vs Instance Store

- Instance store volumes are sometimes called Ephemeral Storage
- Instance store volumes cannot be stopped. If the underlying host fails, You will lose your data
- EBS bakced instances can be stopped. You will not lose the data on this instance if it is stopped
- You can reboot both, You will not lose your data
- Default, both ROOT volumes will be deleted on termination
  - However, With EBS volumes, you can tell AWS to keep the root device volume

## Encrypting Root Device Volumes

- used for monitoring performance
- can monitor most of AWS as well as your applications that run on AWS
- With EC2 will monitor events every 5 minutes by default
- Can have 1 minute intervals by turning on detailed monitoring
- Can create alarms which trigger notifications
- __CloudWatch is all about performance. CloudTrail is all about auditing (API call)__

## What can I do with CloudWatch

- Dashboards
  - Creates awesome dashboards to see what is happening with your AWS environment
- Alarms
  - Allows you to set Alarms that notify you when particular thresholds are hit
- Events
  - Helps you to respond to state changes in your AWS resources

## The CLI

- Can interact with AWS from anywhere in the world just by using the command line (CLI)
- Will need to setup access in IAM
- Commands themselves are not in the exam, but some basic commands will be useful to know for real life

## Roles

- Roles are more secure than storing your access key and secret access key on individeal EC2 instances
- Roles are easier to manage
- Roles can be assigned to an EC2 instance after it is created using both the console and command line
- Roles are universal
  - You can use them in any region

## BootStrap Scripts

- Run when an EC2 instance first boots
- Can be a powerful way of automating software installs and updates

## Instance Meta Data And User Data

- Used to get information about an instance (such as public ip)
- curl <http://169.254.169.254/latest/meta-data>
- curl <http://169.254.169.254/latest/user-data>

## EFS

- Supports the Network File System version 4 (NFSv4) protocol
- You only pay for the storage you use (on pre-provisioning required)
- Can scale up to the petabytes
- Can support thousands of concurrent NFS connections
- Data is tored across multiple AZ/s within a region
- Read after write consistency

## EC2 Placement Groups

### Three types of Placement Groups

- Clustered placement group
  - Low Network Latency / High Network Throughput
  - Can NOT span multiple AZ
- Spread placement group
  - Individual Critical EC2 instances
  - Can span multiple AZ
- Patitioned
  - Multiple EC2 instances HDFS, Hbase, and Cassandra
  - Can span multiple AZ

- The name you specify for a placement group must be unique within your AWS accout
- Only certain types of instances can be lauched in a placement group (Compute Optimized, GPU, Memory Optimized, Storage Optimized)
- AWS recommend homogeous instances within clustered placement groups
- You can't merge placement groups
- You can't move an existing instance into a placement group.
  - You can create an AMI from your existing instance, and then launch a new instance from the AMI into a placement group.
