deploy-aws-infra
================

This role deploys the underlying OCP required Infrastructure in AWS based in the variables defined in the inventory:

Even this role is meant to be used for Red Hat Open Innovation Labs and Emerging Technology Labs, it should be agnostic to be used for any other inventory.

As this is a shared environment, specific tags not related to OCP are added as well to every ec2 and ebs created objects so they can be easily identified. These can be found and modified under 'instance_tags' option on every ec2 instance creation.

Requirements
------------

Ansible version >= 2.4

Role Variables
--------------

| Variable        | Description                           |
|:---------------:|:-------------------------------------:|
|**aws_image_name**| aws ec2 AMI ID
|**aws_num_masters**| number of OCP Master instances to be deployed
|**aws_num_nodes**| number of OCP Compute Node instances to be deployed
|**aws_num_infra**| number of OCP Infra Node instances to be deployed
|**aws_access_key**| aws access key ID
|**aws_secret_key**| aws Secret access key
|**aws_region**| aws Region where to deploy the Infrastructure
|**aws_key_name**| aws Key pair name to be used with the instances
|**aws_subnet**| aws Subnet ID (this value is ignored in case 'aws_create_vpc: true')
|**aws_create_vpc**| either to create the VPC to be used by the OCP Infrastructure &#45; true &#124; false
|**aws_master_sgroups**| aws security groups assigned to Master instances
|**aws_infra_sgroups**| aws security groups assigned to Infra Node instances
|**aws_node_sgroups**| aws security groups assigned to Compute Node instances
|**env_id**| environment ID to use for the Cluster
|**public_dns_domain**| public DNS Zone where to register de Cluster
|**ha_mode**| either to create an HA Cluster or not &#45; true &#124; false
