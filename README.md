# devops-pairing-exercise

In this exercise, we will set up an environment from scratch, add bastion hosts, deploy a service 
and configure load balancing to allow access from outside networks.
We expect services to run in protected, non visible networks, whilst internet - facing services will bridged from public networks.

## Approach

You may implement the tasks using the following approaches:

* manual set up with AWS console
* Ansible/Puppet/Chef scripts
* AWS SDK, or implementation thereof such as boto3
* Terraform
* CloudFormation

You may use pre-existing code base from your own projects, as long as you have ownership/authorship. We will not retain a copy, 
but we need to understand what the code does during the pairing execise to asses the merits of your work.

## Task specifics

1. Create a VPC with two AZs. The VPC should implement the concept of redundant DMZs, i.e. mirroring across AZs.
2. Implement a secure bastion host with an ELB. The bastion host(s) should be HA and offer SSH access through the ELB. 
The instances should be secured, i.e. should not reside in DMZ (public) subnets. The bastion hosts should define dedicated security groups 
that limit access to and from the bastion hosts.
3. Deploy a Jenkins instance. You can either download jenkins from https://jenkins.io/download/ and deploy it onto an EC2 or a Beanstalk instance, 
or deploy a docker container as provided from https://hub.docker.com/r/jenkins/jenkins/ and deploy it onto ECS.
4. Create an external, internet-facing ALB configuration that points to your Jenkins instance 
5. Limit access to your Jenkins to the service ports and SSH.
6. Configure your Jenkins running instance (EC2 or ECS) to only accept SSH connections from your bastion hosts.

## Acceptance

We will verify the follwing outcomes:
* The VPC has the desired strcuture
* We can connect to the bastion host(s) with a provided SSH key
* We can point a browser to provided URL and see the jenkins page, as served by an LB within the VPC.
* We can connect from the bastion host to the instance serving jenkins with our key via SSH
* The bastion host(s) is/are secure
* The Jenkins serving instance is secure
