op-network
==============


## Description
Layers a Public and Private VPC, a NAT server, and a VPN server


## Hierarchy
![composite inheritance hierarchy](https://raw.githubusercontent.com/CloudCoreo/op-network/master/images/hierarchy.png "composite inheritance hierarchy")



## Required variables with no default

### `BACKUP_BUCKET`:
  * description: the name of the bucket in which we should back things up

### `BACKUP_BUCKET_REGION`:
  * description: the region where there vpn backups bucket was created

### `VPN_KEY_BUCKET`:
  * description: the name of the bucket in which we should retrieve and/or store vpn keys

### `VPN_KEY_BUCKET_REGION`:
  * description: the region where there vpn key bucket was created

### `DNS_ZONE`:
  * description: the dns entry for the zone (i.e. example.com)

### `VPN_SSH_KEY_NAME`:
  * description: What key should the vpn instance be launched with?

### `NAT_KEY`:
  * description: The name of the key to use for the nat box


## Required variables with default

### `VPC_NAME`:
  * description: the name of the VPC
  * default: op-vpc


### `VPC_OCTETS`:
  * description: the /16 net of the VPC to look for - i.e 123.123.0.0
  * default: 10.113.0.0


### `PRIVATE_ROUTE_NAME`:
  * description: the name to give to the private route
  * default: op-private-route


### `PRIVATE_SUBNET_NAME`:
  * description: the cloudcoreo name of the private vpc subnets
  * default: op-private-subnet


### `NAT_SG_NAME`:
  * description: the name of the security group to create for the NAT
  * default: op-NAT-sg


### `NAT_INGRESS_PORTS`:
  * description: allowed ingress ports on the nat
  * default: 0..65535

### `NAT_INGRESS_CIDRS`:
  * description: allowed ingress network cidrs on the nat
  * default: 0.0.0.0/0

### `NAT_EGRESS_PORTS`:
  * description: allowed ingress ports on the nat
  * default: 0..65535

### `NAT_EGRESS_CIDRS`:
  * description: allowed ingress network cidrs on the nat
  * default: 0.0.0.0/0

### `NAT_NAME`:
  * description: the name of the nat instance
  * default: op-NAT


### `NAT_SIZE`:
  * description: the instance size of the nat
  * default: t2.small


### `NAT_GROUP_SIZE_MIN`:
  * description: the miniumum number of NAT instances to launch
  * default: 1

### `NAT_GROUP_SIZE_MAX`:
  * description: the maximum number of NAT instances to launch
  * default: 1

### `PUBLIC_SUBNET_NAME`:
  * description: the cloudcoreo name of the public vpc subnets
  * default: op-public-subnet


### `VPN_NAME`:
  * description: the name of the vpn server to launch
  * default: op-vpn


### `VPN_ACCESS_CIDRS`:
  * description: 
  * default: 0.0.0.0/0

### `VPN_SSH_ACCESS_CIDRS`:
  * description: The cidrs from where you should be able to ssh in
  * default: 10.0.0.0/8

### `VPN_INSTANCE_TYPE`:
  * description: 
  * default: t2.micro


### `PUBLIC_ROUTE_NAME`:
  * description: the name to give to the public route
  * default: op-public-route


### `TIMEZONE`:
  * description: the timezone the servers should come up in
  * default: America/Los_Angeles


### `MONITORINTERVAL`:
  * description: time in seconds between route checks
  * default: 20

### `PRIVATE_SUBNETS`:
  * description: 
  * default: COMPOSITE::coreo_aws_vpc_subnet.op-private-subnet.subnet_ids


### `VPN_BACKUP_CRON`:
  * description: the cron schedule for backups
  * default: 0 * * * *

### `ENV`:
  * description: 
  * default: test


### `REGION`:
  * description: the region we are launching in
  * default: PLAN::region

### `VPN_DNS_PREFIX`:
  * description: the dns entry to create for the VPN server (<prefix>.<zone>)
  * default: op-vpn



## Optional variables with no default

### `LOGFILE`:
  * description: ha-nat log file
  * default: /var/log/ha-nat.log


### `VPN_ROUTING_CIDR`:
  * description: This is the cidr of the network cidr the VPN should on your network. i.e. all traffic to this cidr will be routed through the VPN. set to 0.0.0.0 for all traffic. This works in conjunction with the VPN_ROUTING_MASK variable.
  * default: 10.0.0.0


### `VPN_ROUTING_MASK`:
  * description: This is the cidr mask of the network cidr the VPN should on your network. i.e. all traffic to this cidr will be routed through the VPN. set to 0 for all traffic. This works in conjunction with the VPN_ROUTING_CIDR variable.


## Optional variables with default

### `NAT_AMI`:
  * description: the ami id of the nat

### `VPN_AMI_ID`:
  * description: the ami id for the VPN server

### `DATADOG_KEY`:
  * description: If you have a datadog key, enter it here and we will install the agent

## Tags
1. Network
1. VPC
1. NAT
1. VPN

## Categories
1. Network



## Diagram
![diagram](https://raw.githubusercontent.com/CloudCoreo/op-network/master/images/diagram.png "diagram")


## Icon


