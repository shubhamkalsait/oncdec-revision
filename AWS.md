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
## IAM - User, Roles, Policies, Group (global, free)

Service based question
What why how(Resources)

Resource based questions
What why how(Steps to create)

User:
Console access
Programatic Access 

## S3 - Simple Storage Service (global, storage, transfer)
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

## EC2 - Elastic Cloud Compute (IAAS) - Region
Instance - Server (VM) - AMI, Instancetype, Basic Conf, SG, KeyPair, Storage
Instance Types - Generall purpose, compute optimise, memory optimise, storage opitmise, graphics optimise
Purchasing Option - 
Placement Group - group
status check - 0/2, 1/2, 2/2

Linux - SSH
Windows - RDP

AMIs -  Default AMIs, Market Place, Core community
Boot device: Instance Store(MEM), EBS Store (Volume)
How to access AMI from another region

## EBS - Elastic Block Storage
Volumes - Increase
Types: 
SSD - GP, PIOPs(bootable)
HDD - ColdHDD, Throughtput (non-bootable)
Magnetic - Standard (bootable)

S3 vs EBS | Object vs Block 
How to access Volume from another region
Snapshot and AMI

Snapshot - Backup 

## EFS - Elastic File System (Managed NFS)
File System

S3 vs EBS vs EFS 

## Load balancing (ELB)
Load balancer (target) - classic(http, https, tcp, udp), application(http, https), network(tcp, udp)
Target group - Targets 

## AutoScaling (AS)

Horizontal Auto Scaling, Vertical Auto Scaling

Static, Dynamic, Scheduled

Launch Configuration, Launch Template - AMIs, Instance Type, Adition Conf, Key Pair, SG, EBS Storage

ASG - Group Size: Min, Max, Desired
    Scaling Policies: Increase and Decrease (Average)
            Condition(CPUUtilization > 80%) - Alarm and Action +1
            Condition(CPUUtlization < 30%) - Alarm and Action -1






