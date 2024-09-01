*** CIDR (Classless Inter Domain Routing) ***
Subnetting:
  * Subnetting helps us divide network into smaller networks/sub networks which we refer as subnet

# SUBNET
* A Subnet is a range of IP addresses in  VPC. Subnets allow you to segment VPC's IP address range into smaller, more manageable sections.
Types of Subnets:
  * Public Subnets: These subnets have access to the internet, usually through an Internet Gateway (IGW).
  * Private Subnets: These subnets are isolated from the internet and typically have access only within the VPC. Resources in private subnets can access the internet through a NAT gateway or NAT instance.

*** DHCP, or Dynamic Host Configuration Protocol ***

# VPC:
* we can  launch AWS resources in a logically isolated virtual network that you've defined.
* A Virtual Private Cloud (VPC) is a virtual network dedicated to  AWS account. It is logically isolated from other virtual networks in the AWS Cloud.
* We  have complete control over virtual networking environment, including the selection of IP address range, creation of subnets, and configuration of route tables and network gateways.

# Route tables:
 * A route table in an AWS VPC (Virtual Private Cloud) is a set of rules, called routes, that determine where network traffic from your subnet or gateway is directed.
 * Destination: The IP address range that traffic is destined for. This could be an IP address, a CIDR block, or a default route (0.0.0.0/0).
  Target: The gateway, network interface, or connection through which the traffic is directed. This could be an internet gateway, a virtual private gateway, a network interface, a NAT gateway, or a peering connection.

# Internetgateway:
  * In that allows communication between instances in your VPC and the internet
  * An Internet Gateway provides a target in your VPC route tables for internet-routable traffic.

# Network Access Control Lists (NACLs)
  * NACLs control traffic at the subnet level within a VPC, providing an additional layer of security by managing access to and from the entire subnet.
  * NACLs are stateless, meaning that return traffic must be explicitly allowed. If you allow inbound traffic from an IP address, you also need to allow outbound traffic to that IP address if you want a response

# VPN
* In AWS, a VPN (Virtual Private Network) enables secure communication between your AWS resources and your on-premises network or other remote networks over the internet or a private network.   

# Site to site vpn:
* AWS Site-to-Site VPN is a fully-managed performant, scalable, secure, and highly-available way to connect your on-premises users and workloads to AWS. When using Site-to-Site VPN you can connect to both Amazon Virtual Private Clouds (Amazon VPCs) with two tunnels per connection for increased redundancy.

# VPC peering:
* A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network. You can create a VPC peering connection between your own VPCs, or with a VPC in another AWS account. The VPCs can be in different Regions (also known as an inter-Region VPC peering connection).

# DMZ(De-militarized zone):
* DMZ stands for Demilitarized Zone. In computer networking, a DMZ is a network configuration that provides a secure zone between the internet and an organization's internal network. The DMZ is a separate network that contains public-facing services such as web servers, email servers, and FTP servers that are accessible from the internet.
* A DMZ (Demilitarized Zone) network in AWS (Amazon Web Services) is a secure network configuration that allows public-facing services, such as web servers or email servers, to be accessed from the internet while protecting the private resources of the organization.

# Colo
* 
