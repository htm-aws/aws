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
  