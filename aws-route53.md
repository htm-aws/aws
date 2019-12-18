# AWS Route53

- ELBs do not have pre-defined IPv4 address; you resolve to them using a DNS name
- Understand the difference between an Alias Record and a CNAME
- Given the choice, always choose an Alias Record over a CNAME

## Common DNS Types

- SOA Records
- NS Records
- A Records
- CNAMES
- MX Records
- PTR Records

## Routing Policies with Route53

- Simple Routing
  - If you choose the simple routing policy you can only have one record with multiple IP addresses
  - If you specify multiple values in a records, Route 53 returns all values to the user in a random order
- Weighted Routing
  - 20%, 80%
- Lantency-based Routing
  - 50ms, 400ms
- Failover Routing
  - Primary
  - Secondary
- Geolocation Routing
  - Regions
- Geoproximity Routing (Traffic flow only)
  - GPS
- Multivalue Answer Routing
  - The same as Simple Routing, except you get Health checks

## Health Checks

- You can set health checks on individual record sets
- If a record set fails a health check it will be removed from Route53 until it passes the health check
- You can set SNS notifications to alert you if a health checdk is failed

## Routing Traffic resoures

- Cloud front
- EC2
- Elastic BeanStalk
- ELB
- RDS
- S3
- WorkMail

## Logging, Monitoring, tagging

- Cloud trail
- Cloud watch
- Tag editor

## Monitoring Health check

- Endpoints
- State of CloudWatch alarm
- Other healcheck (calculate)
