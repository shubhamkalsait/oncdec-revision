# AWS Revision Sessions

Cloud Computing - Someone else computer that we use through internet
IAAS - Infrastructure as a service
PAAS - Platform as a service
SAAS - Software as service

Private Cloud 
Public Cloud 
Hybrid Cloud
Community Cloud

AWS, GCP, Azure, Alibaba, IBM

1. AWS well matured
2. 400+ Services
3. EC2, light sail
4. 40% AWS
----------------------

AWS - Account 

Services - Resources
1) IAM - User, Roles, Policies, Group (global, free)

Service based question
What why how(Resources)

Resource based questions
What why how(Steps to create)

User:
Console access
Programatic Access 

2) S3 - Simple Storage Service (global, storage, transfer)
Bucket (Region) max 100 buckets, uniq Name
Object Storage,  5 GB / 5 TB
Features: Durability, Scalability, Availability 
Properties: Serverless hosting, Server Access logging, Versioning, Transfer Accelaration, Requester Pays

How to create?

Serverless Hosting:
Bucket,
Upload all the 
Public access enable
make Objects public
Static website hosting enable
Get URL

How to provide access of bucket from one account to another? H.W.

Identity based policy - Users, roles, groups
Resource based policy - Bucket Policy

Lifecycle Rule | Storage classes | How to optimise AWS cost

classes (advantages, Costing)
Frequently Access - Standard, Reduced redundancy
In Frequent Access - Standard-IA, Onezone IA
Archive - Flexible, Glacier, Deep Glacier

Upload - Standard - Standard IA - Glacier - Expire