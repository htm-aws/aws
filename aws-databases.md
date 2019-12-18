# AWS Database

- __RDS (OLTP) - Online Transaction Processing__
  - SQL
  - MySQL
  - PostgreSQL
  - Oracle
  - Aurora
  - MariaDB
- __DynamoDB (No SQL)__
- __Red Shift (OLAP) - Online Analystics Processing__
- __Elasticache__
  - Memcached
  - Redis

## Relational Database

- RDS runs on virtual machines
- You cannot log in to these operation systems however
- Patching of the RDS OS and DB is Amazon's responsibility
- RDS is NOT Serverless
- Aurora Serverless IS Serverless

## 2 types of Backups for RDS

- __Automated Backups__
- __Database Snapshots__

## Read Replicas

- Can be Multi-AZ
- Used to increase performance
- Must have backups turned on
- Can be in different regions
- Can be MySQL, PostgreSQL, MariaDB, Oracle, Aurora
- Can be promoted to master, this will break the Read Replica

## MultiAZ

- Used for DR
- You can force a failover from one AZ to another by rebooting the RDS instance

## Encryption

- Encryption at rest is supported for MySQL, Oracle, SQL Server, PostgreSQL, MariaDB & Aurora
- Encryption is done using the AWS Key Management Service (KMS) service.
- Once your RDS instance is encrypted, the data stored at rest in the underlying storage is encrypted, as are its automated backups, read replicas, and snapshots

## DynamoDB (No SQL)

- Stored on SSD storage
- Spread across 3 geographically distinct data centres
- Eventual consistent reads (default) (best read performance)
  - Đọc tất cả các dữ liệu sao chép thường trong 1s.
  - Lặp lại đọc sau một thời gian ngắn rồi update lại data.
- Strongly consistent reads
  - Trả về một kết quả phản ánh tất cả phản hổi thành công trước khi đọc

## Redshift

- Redshift is used for business intelligence
- Available in only 1 AZ
- __Backups__
  - Enabled by default with a 1 day retention period
  - Maximum retention period is 35 days
  - Always attempts to maintain at least three copies of your data (the original and replica on the compute nodes and a backup in Amazon S3)
  - Can also asynchronously replicate your snapshots to S3 in another region for disaster recovery

## Aurora

- 2 copies of your data is contained in each availability zone, with min of 3 availability zones. 6 copies of your data.
- You can share Aurora Snapshots with other AWS accounts
- 2 types of replicas available. Aurora Replicas and MySQL replicas. Automated failover is only available with Aurora Replicas
- Aurora has automated backups turned on by default. You can also take snapshots with Aurora. You can share these snapshots with other AWS accounts.

## Elasticache

- Use Elasticache to increase database and web application performance
- Redis is Multi-AZ
- You can do backups and restores of Redis
- If you need to scale horizontally, use Memcached
