manage-aws-infra
================

This role manages the underlying OCP Infrastructure in AWS that has been deployed using the ['deploy-aws-infra'](../deploy-aws-infra) role. Using the value from 'operation' variable, the role will start, stop or destroy the underlying OCP Cluster Infrastructure.

Even this role is meant to be used for Red Hat Open Innovation Labs and Emerging Technology Labs, it should be agnostic to be used for any other inventory.

As this is a shared environment, specific tag, 'env_id', is used to determine the AWS objects to manage. This tag corresponds with the 'env_id' variable from the inventory.

Requirements
------------

Ansible version >= 2.4

Role Variables
--------------

| Variable        | Description                           |
|:---------------:|:-------------------------------------:|
|**aws_access_key**| aws Access key ID|
|**aws_secret_key**| aws Secret access key|
|**aws_region**| aws Region where to deploy the Infrastructure|
|**env_id**| environment ID to use for the Cluster|
|**operation**| action to perform with the Cluster &#45; running, stopped or absent|
|**delete_vpc**| boolean to remove or not the VPC used for the Cluster &#45; true &#124; false|
