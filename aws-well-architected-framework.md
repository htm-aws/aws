# AWS Well-Architected Framework

## Operational Excellence (Hoạt động xuất sắc)

The ability to run and monitor systems to deliver
business value and to continually improve supporting
processes and procedures.

### Key AWS Services

- AWS CloudFormation:
  - You can use to create templates based on best practices
  - This enables you to provision resources in an orderly and consistent fashion from your development through production environments
  - The following services and features support the three areas in operational excellence:
    - __Prepare__: AWS Config and AWS Config rules can be used to create standards for workloads and to determine if environments are ompliant with those standards before being put into production
    - __Operate__: Amazon CloudWatch allows you to monitor the operational health of a workload
    - __Evolve__: Amazon Elasticsearch Service (Amazon ES) allows you to analyze your log data to gain actionable insights quickly and securely

## Security (Bảo mật)

The ability to protect information, systems, and assets
while delivering business value through risk assessments
and mitigation strategies

### Key AWS Services

- AWS Identity and Access Management (IAM):
  - which allows you to securely control access to AWS services and resources for your users.
  - The following services and features support the five areas in security:
    - __Identity and Access Management__:
      - IAM enables you to securely control access to AWS services and resources
      - MFA adds an additional layer of protection on user access
      - AWS Organizations lets you centrally manage and enforce policies for multiple AWS accounts
    - __Detective Controls__:
      - AWS CloudTrail records AWS API calls, AWS Config provides a detailed inventory of your AWS resources and configuration
      - Amazon GuardDuty is a managed threat detection service that continuously monitors for malicious or unauthorized behavior
      - Amazon CloudWatch is a monitoring service for AWS resources which can trigger CloudWatch Events to automate security responses
    - __Infrastructure Protection__:
      - Amazon Virtual Private Cloud (Amazon VPC) enables you to launch AWS resources into a virtual network that you've defined
      - Amazon CloudFront is a global content delivery network that securely delivers data, videos, applications, and APIs to your viewers which integrates with AWS Shield for DDoS mitigation
      - AWS WAF is a web application firewall that is deployed on either Amazon CloudFront or Application Load Balancer to help protect your web applications from common web exploits
    - __Data Protection__:
      - Services such as ELB, Amazon Elastic Block Store (Amazon EBS), Amazon S3, and Amazon Relational Database Service (Amazon RDS) include encryption capabilities to protect your data in transit and at rest
      - Amazon Macie automatically discovers, classifies and protects sensitive data, while AWS Key  Management Service (AWS KMS) makes it  asy for you to create and control keys used for encryption
    - __Incident Response__:
      - IAM should be used to grant appropriate authorization to incident response teams and response tools
      - AWS CloudFormation can be used to create a trusted environment or clean room for conducting investigations
      - Amazon CloudWatch Events allows you to create rules that trigger automated responses including AWS Lambda

## Reliability (Tin cậy)

The ability of a system to recover from infrastructure
or service disruptions, dynamically acquire computing
resources to meet demand, and mitigate disruptions
such as misconfigurations or transient network issues.

### Key AWS Services

- Amazon CloudWatch:
  - Which monitors runtime metrics
  - The following services and features support the three areas in reliability:
    - __Foundations__:
      - AWS IAM enables you to securely control access to AWS services and resources
      - Amazon VPC lets you provision a private, isolated section of the AWS Cloud where you can launch AWS resources in a virtual network
      - AWS Trusted Advisor provides visibility into service limits
      - AWS Shield is a managed Distributed Denial of Service (DDoS) protection service that safeguards web applications running on AWS 
    - __Change Management__:
      - AWS CloudTrail records AWS API calls for your account and delivers log files to you for auditing
      - AWS Config provides a detailed inventory of your AWS resources and configuration, and continuously records configuration changes

## Performance Efficiency (Hiệu suất hiệu quả)

The ability to use computing resources efficiently
to meet system requirements, and to maintain that
efficiency as demand changes and technologies evolve.

- Amazon CloudWatch:
  - Which monitors your resources and systems, providing visibility into your overall performance and operational health
  - The following services and features support the four areas in performance efficiency:
    - __Selection__:
      - __Compute__: Auto Scaling is key to ensuring that you have enough instances to meet demand and maintain responsiveness
      - __Storage__: Amazon EBS provides a wide range of storage options (such as SSD and provisioned input/output operations per second (PIOPS)) that allow you to optimize for your  use case. Amazon S3 provides serverless content delivery, and Amazon S3 transfer acceleration enables fast, easy, and secure transfers of files over long distances
      - __Database__: Amazon RDS provides a wide range of database features (such as PIOPS and read replicas) that allow you to optimize for your use case. Amazon DynamoDB provides single-digit millisecond latency at any scale.
      - __Network__: Amazon Route 53 provides latency-based routing. Amazon VPC endpoints and AWS Direct Connect can reduce network distance or jitter
    - __Review__:
      - The AWS Blog and the What's New section on the AWS website are resources for learning about newly launched features and services
    - __Monitoring__:
      - Amazon CloudWatch provides metrics, alarms, and notifications that you can integrate with your existing monitoring solution, and that you can use with AWS Lambda to trigger actions
    - __Tradeoffs__:
      - Amazon ElastiCache, Amazon CloudFront, and AWS Snowball are services that allow you to improve performance.
      - Read replicas in Amazon RDS can allow you to scale read-heavy workloads

## Cost Optimization (Tối ưu chi phí)

The ability to run systems to deliver business value at
the lowest price point

### Key AWS Services

- Cost Explorer
  - Which helps you gain visibility and insights into your usage, across your workloads and throughout your organization.
  - The following services and features support the four areas in cost optimization:
    - __Expenditure Awareness__:
      - AWS Cost Explorer allows you to view and track your usage in detail.
      - AWS Budgets notify you if your usage or spend exceeds actual or forecast budgeted amounts
    - __Cost-Effective Resources__:
      - You can use Cost Explorer for Reserved Instance recommendations, and see patterns in how much you spend on AWS resources over time
      - Use Amazon CloudWatch and Trusted Advisor to help right size your resources
      - You can use Amazon Aurora on RDS to remove database licensing costs
      - AWS Direct Connect and Amazon CloudFront can be used to optimize data transfer
    - __Matching supply and demand__:
      - Auto Scaling allows you to add or remove resources to match demand without overspending
    - __Optimizing Over Time__:
      - The AWS News Blog and the What's New section on the AWS website are resources for learning about newly launched features and services.
      - AWS Trusted Advisor inspects your AWS environment and finds opportunities to save you money by eliminating unused or idle resources or committing to Reserved Instance capacity
