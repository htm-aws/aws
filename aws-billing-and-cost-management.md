# AWS Billing and Cost Management

- __Cost Explorer__ tracks and analyzes your AWS usage. It is free for all accounts.
- Use __Budgets__ to manage budgets for your account.
- Use __Bills__ to see details about your current charges.
- Use __Payment History__ to see your past payment transactions.

## AWS Free Tier

- When you create an AWS account, you’re automatically signed up for the free tier for __12 months__.

## AWS Cost Explorer

- Other default reports available are:
  - The __EC2 Monthly Cost and Usage__ report__ lets you view all of your AWS costs over the past two months, as well as your current month-to-date costs.
  - The dsd

## AMI

- Includes the following:
  - Launch permissions that control which AWS accounts can use the AMI to launch instances
  - A template for the root volume for the instance (OS, application server, and applications)
  - A block device mapping that specifies the volumes to attach to the instance when it’s launched
      ![img1](https://k2y3h8q6.stackpathcdn.com/wp-content/uploads/2018/12/AWS-Training-Amazon-EC2-2.jpg)
  - Backed by Amazon EBS – root device for an instance launched from the AMI is an Amazon EBS volume. AMIs backed by Amazon EBS snapshots can use EBS encryption.
  - Backed by Instance Store – root device for an instance launched from the AMI is an instance store volume created from a template stored in S3.
      ![img2](https://k2y3h8q6.stackpathcdn.com/wp-content/uploads/2018/12/AWS-Training-Amazon-EC2-3.jpg)
  - You can copy AMIs to different regions.
