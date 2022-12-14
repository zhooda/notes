- VPC (Virtual Private Cloud)
	- virtual datacenter in the cloud
	- logically isolated part of AWS cloud
	- define your own network
	- complete control of network
		- IP ranges
		- subnets
		- route tables
		- network gateways
- networking
	- fully customizable network
	- leverage multiple layers of security
		- security groups
		- network [[Access Control Lists|ACL]]s
	- 3-tier architecture
		- Web tier (80/443) - public facing subnet
		- Application Tier - private subnet, can only speak to Web tier and Database tier
		- Database Tier - private subnet, can only speak to Application tier
	- [[CIDR]] ranges
		- smallest subnet `10.0.0.0/28` - 16 addresses
		- largest  subnet `10.0.0.0/16` - 65,536 addresses
- VPNs
	- create hardware VPN connection between corporate data center and AWS VPC
	- leverage AWS cloud as extension of corporate data center
- Network Diagram
	- ![[Pasted image 20221024134046.png]]
- VPC features
	- launch instances into subnet
	- create custom IP ranges for each subnet
	- configure route tables between subnets
	- attach internet gateway to VPC
	- more control and security over AWS resources
	- provision [[Access Control Lists]]
		- block specific IPs using N[[Access Control Lists|ACL]]s
- Comparing VPCs
	- default
		- every account comes with default VPC
		- all subnets in default VPC have route to internet
		- each EC2 instance has a public and private address
	- custom
		- fully customizable
		- takes time to set up

Review
- VPC = logical data center in AWS
- consists of
	- internet gateways
	- route tables
	- network [[Access Control Lists]]
	- subnets
	- security groups
- 1 subnet is always in 1 [[availability zone]]