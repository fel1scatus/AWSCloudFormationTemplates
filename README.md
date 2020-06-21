# AWSCloudFormationTemplates

This is the main repository for all my custom made AWS CloudFormation Templates.

Most of them will be part of labs.

How to use?

Create a new Stack in CloudFormation and upload the YAML template.

More information:

https://docs.aws.amazon.com/cloudformation/index.html




#About "VPCPeeringLabPart1.yml"

  This Cloud Formation template is part 1 of a lab to test VPC Peering.
  
  It creates the following infrastructure in the AWS Cloud:  

  In the US-East-1 region.  
  3 VPCs with different /16 CIDR ranges.  
  1 subnet per VPC using the first /24 network block from the VPC range with public addresses assignement enabled.  
  1 Internet Gateway per VPC and attaches it to each VPC.  
  1 Route table for each VPC. Which points to the IGW, and it is then associated one per subnet.  
  3 Security Groups to allow access from the internet over SSH using a parameter specified IP address given at the time of the stack's creation, and rules allowing ICMP traffic against part of the neighbor VPCs.  
  3 Linux t2.micro instances, one per VPC, with the mentioned security groups and a parameter specified KeyPair which is promped at the time of the stack's creation.
  
  
#About "VPCPeeringLabPart2.yml"

  This template is the part 2 of the lab to test VPC Peering.

  It creates the following:
  
  In the US-East-1 region.
  2 Peering connections for VPCs created with the Part 1 template. One for VPCs A with B, and the other for VPCs B with C.
  4 Routes added to the route tables from Part 1 template. To and from A with B, and to and from B with C.
  The Peering connection IDs are the output from this stack.
  
