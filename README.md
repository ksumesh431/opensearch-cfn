OpenSearch CloudFormation Template
=================================

This CloudFormation template creates an OpenSearch domain with an associated IAM service-linked role and domain policy.

 Parameters
------------

The following parameters are available:

### OpenSearch Configuration

* **DomainName**: The name of the OpenSearch domain
* **EngineVersion**: The version of OpenSearch to deploy
* **InstanceType**: The instance type for the OpenSearch cluster
* **InstanceCount**: The number of instances in the OpenSearch cluster
* **DedicatedMasterEnabledParam**: Whether to enable dedicated master nodes
* **DedicatedMasterType**: The instance type for the dedicated master nodes
* **DedicatedMasterCount**: The number of dedicated master nodes (Minimum 2)
* **ZoneAwarenessEnabled**: Whether to enable zone awareness
* **AvailabilityZoneCount**: The number of availability zones for the domain
* **EBSVolumeType**: The EBS volume type for the OpenSearch domain
* **EBSVolumeSize**: The size of the EBS volume (in GB)
* **EBSEnabled**: Whether to enable EBS volumes
* **Iops**: Iops for the EBS volume
* **Throughput**: The throughput of the EBS volume
* **EnforceHTTPS**: Whether to enforce HTTPS
* **TLSSecurityPolicy**: The TLS security policy to use
* **AdvancedSecurityEnabled**: Whether to enable advanced security options
* **InternalUserDatabaseEnabled**: Whether to enable the internal user database
* **NodeToNodeEncryptionEnabled**: Whether to enable node-to-node encryption
* **EncryptionAtRestEnabled**: Whether to enable encryption at rest
* **CustomEndpointEnabled**: Whether to enable a custom endpoint
* **AwsServiceNameForLinkedRole**: The AWS service name for the linked role
* **AnonymousAuthEnabled**: Whether to enable anonymous access

### VPC Configuration

* **VpcId**: The ID of the VPC
* **SubnetIds**: The IDs of the subnets
* **SecurityGroupIds**: The IDs of the security groups

 Resources
------------

The following resources are created:

* **OpenSearchServiceLinkedRole**: An IAM service-linked role for OpenSearch
* **OpenSearchDomain**: An OpenSearch domain with the specified configuration

 Conditions
------------

The following conditions are used:

* **ShouldCreateServiceLinkedRole**: Whether to create the service-linked role
* **ShouldCreateZoneAwarenessOpenSearch**: Whether to create the OpenSearch domain with zone awareness
* **ShouldNotCreateZoneAwarenessOpenSearch**: Whether to create the OpenSearch domain without zone awareness
* **EnableDedicatedMaster**: Whether to enable dedicated master nodes

Please note that this template creates a OpenSearch domain with a service-linked role and a access policy.