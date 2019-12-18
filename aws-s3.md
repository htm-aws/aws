# Amazon S3

- S3 is __Object-based__. i.e. allows you to upload files
- Max 100 buckets in each AWS accounts
- Files can be from 0B-5TB:
  - For objects > 100 MB: should use the __Multipart Upload__
- There is unlimited storage
- Files are stored in Buckets
- __S3 is universal namespace__. That is names must be unique globally
- __Not suitable to install an operating system on__
- Sucessful uploads will generate a __HTTP 200__ status code
- By default, all newly created buckets are __PRIVATE__. You can setup access control to you buckets using:
  - __Bucket policies__
  - __Access control lists__
- S3 buckets can be configured to create access logs which log all requests made to the S3 bucket. This can be sent to another bucket and even another bucket in another account
- S3 notification publish events:
  - SNS
  - SQS
  - Lambda
- To avoid accidental deletion:
  - Enable Versioning
  - Enable MFA (Multi-Factor Authentication) Delete
- Access a Bucket:
  - Virtual-hosted-style URL: <http://bucket-name.s3-aws-region.amazonaws.com>
  - Path-style URL: <http://s3.aws-region.amazonaws.com/bucket-name>

## Key Funcdamentals of S3

- Key (this is simply the name of the object)
- Value (this is simply the data and is made up of a sequence of bytes)
- Version ID (important for versioning)
- Metadata (data about data you are storing):
  - System metadata
  - User-defined metadata: __x-amz-meta-__[x-amz-key]
- Subresources:
  - Access control lists
  - Torrent
- Read after Write consistency for PUTS of new objects
- eventual consistency for overwrite PUTS and DELETES (can take some time to propagate)

## Storage Classes

- S3 Standard
- S3 - IA
- S3 One Zone - IA
- S3 - Intelligent Tiering
- S3 Glacier:
  - Expedited (1-5 minutes)
  - Stansard (3-5h)
  - Bulk (5-12h)
- S3 Glacier Deep Archive

## Security & Encryption

- Encryption in Transit is achieved by __SSL/TLS__
- Server side encyption via:
  - Amazon S3-managed keys (__SSE-S3__) (AES-256)
  - AWS KMS-managed Keys (__SSE-KMS__)
  - Customer-provided keys (__SSE-C__)
- Client side encryption via:
  - AWS KMS-managed keys
  - Customer-supplied client-side master keys

## Cross region replication

- Versioning must be enabled on both the source and destination buckets
- Region must be unique
- Files in an existing bucket are not replicated automatically
- All subsequent updated files will be replicated automatically
- Delete markers are not replicated
- Deleting individual versions or delete markers will not be replicated
- Understand what cross region replication is at a high level

## Lifecycle Policies

- Automates moving your objects between the different storage tiers.
- Can be used in conjunction with versioning
- Can be applied to current versions and previous verions
- Add:
  - S3 -> S3-IA, S3 One Zone - IA (at least 30 days)
  - S3 -> Flacier after 7days

## CloudFront

- Edge Location
  - This is the location where content will be cached. This is separate to an AWS region/AZ
- Origin
  - This is the origin of all the files that the CDN will distribute. This can be either an S3 Bucket, an EC2 instance, and Elastic Load Balancer, Route 53
- Distribution
  - This is the name given the CDN which consists of a collection of Edge Locations
- Web Distribution
  - Typically used for Websites
- RTMP
  - Used for Media Streaming

- Edge location are not just READ only - you can write to them too (ie put an object on to them)
- Objects are cached for the life of the __TTL (Time To Live)__
- You can clear cached objects, but you will be charged
- Amazon S3 Transfer Acceleration enables fast, easy, and secure transfers of files over long distances between your client and your Amazon S3 bucket

## Snowball

- Snow ball Can
  - Import to S3
  - Export from S3

## Storage Gateway

- __File Gateway__
  - for flat files, stored deirectly on S3
- __Volume Gateway__
  - __Storage Volumes__
    - Entire Dataset is stored on site and is asynchronously backed up to S3
  - __Cached Volumes__
    - Entire Dataset is stored on S3 and the most frequently accessed data is cached on site
- __Gateway virtual tap library__
  - Used for backup and uses popular backup applications like NetBackup, Backup Exec, Veeam etc
