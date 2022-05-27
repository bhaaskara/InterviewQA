![[Pasted image 20220306000029.png]]

# EC2
## Public IP vs Elastic IP?
**Public IP** is required, if you need the EC2 instance have direct communication with the open internet.
This IP address will be lost if the instance is terminated.

**Elastic IP** is a static public IPv4 address.
this can be detached from an instance and attached to another instance.

# VPC
## What is VPC?
A private subsection of AWS that you can control, in which you can place AWS resources.

## Subnet
### What is AWS subnet?
A subnet is **a range of IP addresses in your VPC**. You can attach AWS resources, such as EC2 instances and RDS DB instances, to subnets. You create subnets to group instances together according to your security and operational needs.