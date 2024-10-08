# DevOps Revision

## Linux 
- Basic Commands: ls, cd, pwd, cp, mv, man
- User Administration: useradd, groupadd, gpasswd -a
- Permission Management: chmod, chown
- Package Management: yum, apt, rpm, deb
- Archiving: gzip, tar
- Cronjob: cron

## AWS
- IAM, S3, EC2, VPC, CloudWatch, RDS, EKS, ECR, Route53, CloudFront, SNS, CloutTrail, EventBridge

## DevOps
Methodology to follow SDLC lifecycle.

SDLC - 
Req gathering and analysis
Plan and Design
Coding and Implimentation
Build
Testing
Dlevery and deployment
Mentainance and Monitoring

Waterfall Model (Steps) - 1 year
- No transpency client 
- No add feature
- Querals/conflicts

Agile Model 
- cycle (2-3month) 
- Client 3 month
- new feature
- Quarals/conflicts

DevOps - Developemnt + Operations
- Agile Model
- cycles (2-3 Week)
- Automations
- Transperncy
- Same env (dev and ops)


CICD: Jenkins, CodePipeline, Cloud Build, AzurePipeline, gitlab-ci
Containerization: Docker, podman, crio, containerd
Orchestration: Kubernetes, OpenShift, dockercompose, dockerswarm
Monitoring: CloudWatch, Grafana, Prometheus, Elastic Search, LogStash, Kibana
SourceCode: git, github, gitlab, btbucket, codecommit, 
IAC: Terraform, CloudFormation
CM: Ansible, chef, puppet
Build: Maven, gradle
Test: Selenium, Sonarqube, postman


SourceCode Management:

Source Code (Application Code) - 

Laptop, Google drive: 

Centralize VCS - Single Repo () - subversion
Distributed VCS - Remote Repo - Local repo - git, bitgucket



## GIT

- How to Install git
- git lifecycle
- git commands


Project:
-------

Client: DYL (CRM)
TechStack: Frontends (5)(Angular), Backend (18)(Springboot), DB (18)(Postgres)
Build Tool (Maven)

Branching Strategy:

 feature
dev - 
test - 
uat - 
prod - 

-----------

git add
git commit 
git push 
git pull
git checkout
git branch
git merge
git fetch
git revert
 
## Docker - Containerisation Tool

Baremetal 
- monolithic / XXX Microservices
- Scalibility
- Effieciency
- Costlier

Virtualization
- Scalable
- Microservices
- Efficiency
- Less costlier
- quarals
- OS 
- Daemons

Containerisation
- app, files, os lib, - container image - container 
- containers - image - containers
- High scalability
- light weight
- 1 Service


Dockerfile
----------

docker images - 
customise, dockerfile

BASE IMAGE
INSTRICTION ARG
from  centos:7
run  yum install httpd -y               (building)
expose 80
copy ./index.html /var/www/html/index.html       (building the docker image)
add https://myfiles.com/image.jpg /var/www/html/image.jpg     (download)                             
EXNTRYPOINT httpd -DFOREGROUND     (running)


USER 
WORKDIR /var/www/html

ENV  - Container running
ARG  - Building

exit()


multistage

light weight

build



studentapp
git
mvn
tomcat

dockerfile

form centos:7
run yum install git maven tomcat -y
run git clone studentapp
run mvn clean package
run cp target/student.war tomcat/webapps
cmd catalina.sh run

from git
run git clone studentapp

From maven as builder
run mvn clean package

from tomcat
copy --from=builder studentapp/target/student.war ./
run cp ./student.war tomcat/webapps
cmd catlina.sh


## Kubernetes
--------------

Orchestration tool 

kubeadm 
minikube 
kind 
EKS
GKE
AKS
------------
Architecture:-

k8s Cluster - two types nodes - workernode and controlplane

Controlplane (API server, etcd, scheduler, controller Manager)
workernode (Kubeproxy, kubelet, Contaier Engine, Pods)

lifecycle of pod
-----------

Objects
-------
- Pods - Wrapper around containers
- Services - ClusterIP, NodePort, Loadbalancer, Headless 
- Deployment - maintain deployment of the pods
- StatefulSet - replicas of stateful pod
- Daemon Set - Create pod on every node
- ReplicaSet - replicas of pod - apps/v1 - set based
- Replication Controller - replicas of pod - v1 - Equality based
- Config Map / Secrets - Variables
- PV / PVC - Persistent Data
- Ingress - Ingress rule
- namespace - Devide cluster
- role, rolebinding, clusterRole, clusterRoleBinding
-------


## Terraform

- IAC - Infrastructure As Code
- Terraform vs Ansible
    IAC | CM
    create resources | configure server
- Terrafor Lifecycle
    terraform init, plan, apply, destroy
- How to remove specific resource?
- Terraform language
.tf / .tf.json

- provider, resource, variables, output, data, module, terraform

provider "aws" {
    access_key_id =
    secret_access_key =
    region = 
}

terraform {
    backend "s3" {
        bucket = 
        region = 
        key = "terraform.tfstate"
    }
}

#resource "aws_instance" "my_instance" {
#    ami = var.images
#    vpc_security_group_id = data.aws_security_group.my_sg.id
#}

instance = t2.micro

resource "aws_instance" "my_instance1" {
    ami = var.images
    vpc_security_group_id = data.aws_security_group.my_sg.id
    instance_type = "t2.micro"
    user_data = <<EOF   
                #!/bin/bash
                yum install httpd -y
                systemctl start httpd
            EOF
    user_data = file("demo.sh")
}

data "aws_security_group" "my_sg" {
    name = "default"
}

variables "images" {
    default = "ami-afhiwh313"
}

output "public_ip" {
    value = aws_instance.my_instance.public_ip 
}
module "my_vpc" {
    source = "./module/instance"
    images = "ami-dfsfk234"
}

dev.tfvar
    images = "ami-dsff234"

export ACCESS_KEY_ID="ajdbfshgo"
export secret_access_key="grkgjdf23423"

terraform apply --var-file dev.tfvar --var access_key_id=$ACCESS_KEY_ID --var seceret_access_key="14b325"

- terraform import

resource "aws_instance" "new_instance" {
    name = "my-instance"
}

terraform.state

- terraform taint
