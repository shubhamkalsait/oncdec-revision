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



## VPC - Virtual Private Cloud

Isolated Network (No Public network)
5 VPC
VPC (region)
Subnet (az)

CIDR - /16

/32 - 1
/31 - 2
/30 - 4
/20 - 4096 - 5 IPs reserved - 4091 - use 
first - network
last - broadcast
second - Routing
third - DNS
foursth - Future

VPC - Infra
Subnets (private and Public) = no default public ip 
Internet Gateway =  
route table 
Nat gateway =
SG
NACL
NI
Elastic IPs
Endpoints
Peering Connection - Different CIDR

Peering connection (requester) - VPC ID (Accepter)
VPC - Webserver  ---> VPC - Database
us-east-1 ---> ap-south-1   


Steps: Create peering connection (Requester and accepter)
Steps: Generate peering request 
Steps: Accept Peering request
Steps: Route traffic route table
Steps: Subnet A will be route in route table B and vice versa


SG vs NACL
----------
1. NI attach  - 2. Subnet Attach
2. Statefull firewall - 2. Stateless Firewall
3. Public Ports are allowed - 3. Allow public port separetly
4. Inbount rule only - 4. inbound and outbound both
5. Allow - 5. Allow / Deny


site to site (VPC - VPC)
client to site (VPC - Laptop)

On prem - VPC -> Transit Gateways

Direct Connect - Nagpur 


Traffic Mirroring -> Traffic Monitoring Server

## CloudWatch

Monitoring and logging service

Dashboard
Alarm  (OK, insuficient data, Alarm)
Metrics (Processed Data)
Logs
Events

metrics

Default Metric      Custom Metric
CPUUtilization      MemoryUtlization 
NetworkIn           StorageUtilization
NetworkOut

Logs (Application logs stream)  /var/log/httpd/
Cloudwatch Agent /var/log/httpd/access.log   error.logss


## RDS (managed Relation Database Service)

Administration AWS

RDS Instance -> SSHXXX

1) No Administration
2) No System Engineer (Human Resource) 
3) Storage AutoScaling (Vertical AutoScaling)
4) Schedule Automated Backups
5) High Availability
6) Easy to manage Read Replicas
7) Auto Minor Upgradation  

## Route53 

DNS and Traffic Routing 

Hosted Zone, Health Checks, Routing Policies

Hosted Zone - Store records

SOA - Start of Authority
NS - Name Server
A - IP to Domain name
AAAA - IPv6 to Domain Name
CNAME - Domain Name to Domain Name
PTR - Domain Name to IP
TXT - Text Record
MX - Mail Exchange Record

Health Checks - ping 
 
http://172.31.0.15 - Notify / Routing Policy


Routing Policy:
-------------

Simple Routing - domain -> domain
Failover -> 
Weighted -> 
Geolocation based -> India / Canada
Geoproximity -> 
Latency -> 
IP-based -> 
multivalue answered -> 


## CloudFront
CDN - Content Delivery Network

Cache Server (Edge location), Distribution


Server (IP) --- LoadBalancer (Endpoint) ---- CDN (endpoint) --- Route53 (endpoint to Domain)

## Lambda - Serverless Computing Service

Java, Python - Server+Environment

(submit) - Code run 

Server Administrate
System Engineer
Env
Install
24X7 Server

- API application
- Boto3 Python (AWS Automate)
    - Backup instace (Event bridge) Stopping - EBS backup
    - DAtabase backup
    - Workign hour,(event bridge) instance stop
    - archiving images, s3 upload (.jpg)
