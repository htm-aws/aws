# Amazon USE CASE

## LOGS

### CloudTrail

- Tracking the __`API calls`__  of your AWS resources

### VPC flow logs

- Tracking the __`traffic comming`__ into the VPC

### CloudWatch

- __`Monitor, store, and access`__ the log files of your instance

### CloudWatch Logs agent

- Provides an automated way to send log data __`to`__ CloudWatch Logs __`from`__ EC2

### KMS vs CloudHSM

- You should consider using __`AWS CloudHSM`__ over _`AWS KMS`_ if you require:
  - Keys stored in dedicated, third-party validated hardware security modules under your exclusive control
  - FIPS 140-2 compliance
  - Integration with applications using PKCS#11, Java JCE, or Microsoft CNG interfaces
  - High-performance in-VPC cryptographic acceleration (bulk crypto)

### Amazon Route 53 currently supports the following DNS record types

- A (address record)
- AAAA (IPv6 address record)
- CNAME (canonical name record)
- CAA (certification authority authorization)
- MX (mail exchange record)
- NAPTR (name authority pointer record)
- NS (name server record)
- PTR (pointer record)
- SOA (start of authority record)
- SPF (sender policy framework)
- SRV (service locator)
- TXT (text record)

### CloudFormation

- Template JSON or a YAML-formatted text file:
  - Format Version
  - Description
  - Metadata
  - Parameters
  - Mappings
  - Conditions
  - Transform
  - Resources (required)
  - Outputs

## Amazon EFS

- __Amazon EFS__ is a fully-managed service that makes it easy to __set up and scale file storage__ in the Amazon Cloud
- __Amazon EFS__ file systems can automatically __scale from gigabytes to petabytes__ of data without needing to provision storage

## SHORT

- __Glacier__ is an archiving storage solution
- __AWS Storage Gateway__ connects an on-premises software appliance with cloud-based storage to provide seamless integration with data security features between your on-premises IT environment and the AWS storage infrastructure
    ![aws-storage-gateway-stored-diagram](https://docs.aws.amazon.com/storagegateway/latest/userguide/images/aws-storage-gateway-stored-diagram.png)

- __EBS__ is primarily used as a storage of your EC2 instances
- __S3 Glacier (Vault Lock)__ policy
    ![aws-storage-gateway-stored-diagram](https://media.amazonwebservices.com/blog/2015/glacier_lock_policy_4.png)

- __Amazon MQ__
  - is a managed message broker service for Apache ActiveMQ that makes it easy to set up and operate message brokers in the cloud.
  - uses industry-standard APIs and protocols for messaging:
    - JMS, NMS, AMQP, STOMP, MQTT, and WebSocket
- __SQS__ is a fully managed message queuing service
- __SNS__ is more suitable as a __pub/sub messaging service__ instead of a __message broker__ service
- __SWF__ is a fully-managed state __tracker and task coordinator service__ and not a messaging service
- __AWS CloudFormation__ is a service that helps you __model and set up your Amazon Web Services resources__ so that you can spend less time managing those resources and more time focusing on your applications that run in AWS
  - You can create a template that describes all the AWS resources that you want (like Amazon EC2 instances or Amazon RDS DB instances), and AWS CloudFormation takes care of provisioning and configuring those resources for you
    ![aws-storage-gateway-stored-diagram](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/images/designer-jsoneditor.png)
  - provides a common language for you to describe and provision all the infrastructure resources in your cloud environment
    ![create-stack-diagram](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/images/create-stack-diagram.png)
- __CloudWatch__ only monitor:  
  - CPU utilization
  - Network utilization
  - Disk performance and Disk Reads/Writes
- __Install CloudWatch Monitoring Scripts in your EC2__ to collect and monitor the custom metric (memory usage)
- __AWS SDK__ is a set of __programming tools__ that allow you to create applications that run using Amazon cloud services
- __Amazon EMR__ is a managed cluster platform that simplifies running big data frameworks, such as Apache Hadoop and Apache Spark, on AWS to process and analyze vast amounts of data
  - you can process data for analytics purposes and business intelligence workloads
- __AWS Step Functions__ provides serverless orchestration for modern applications. Orchestration centrally manages a workflow by breaking it into multiple steps, adding flow logic, and tracking the inputs and outputs between the steps
- __Lambda__ is used for serverless computing, it does not provide a direct way to coordinate multiple AWS services into serverless workflows
- __AWS Batch__ is primarily used to efficiently run hundreds of thousands of batch computing jobs in AWS.
- __Elastic Beanstalk__ is fastest and simplest way to __deploy your application__ on AWS
- __AWS (Amazon Web Services)__ is a secure cloud services platform, offering compute power, database storage, content delivery and other functionality to help business scale and grow. (là một nền tảng dịch vụ đám mây bảo mật, cung cấp sức mạnh tính toán, lưu trữ cơ sở dữ liệu, phân phối nội dung và các chức năng khác để giúp doanh nghiệp mở rộng và phát triển)
- __CloudWatch__ is the component of AWS that provides real time monitoring of AWS resources and customer applications running on Amazon infrastructure
- __CloudWatch Logs__ is used to monitor, store and access log files from AWS resources like EC2, CloudTrail, Route53 and others
- __Snaphosts__ only capture data that has been written to your EBS volume at the time the __snapshot__ command is issued. (Chỉ thu thập dữ liệu đã được ghi vào ổ đĩa EBS của bạn tại thời điểm lệnh snapshot được ban hành)
- An __Amazon Machine Image (AMI)__ is a special type of virtual appliance that is used to instantiate (create) a virtual machine within EC2. It serves as the basic unit of deployment for services delivered using EC2. (Là một loại thiết bị ảo đặc biệt sử dụng để khởi tạo (tạo) một máy ảo trong EC2. Nó đóng vai trò là đơn vị triển khai cơ bản cho các dịch vụ được cung cấp bằng EC2)
- __Simple Notification Service (SNS)__ for short is a flexible fully managed pub/sub messaging service what that means is that you can create a topic and users subscribe to that topic and when you publish a message to the topic the users that have subscribed to that topic will receive that message it can also be used for push notifications for mobile devices
- __SQS__ for short is a fully managed Message Queuing service and that makes it easy to decouple your applications from demand what that means is that it allows messages to build up in a queue until the processing server that processes those messages can catch up with the demand
