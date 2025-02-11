![test](./Pasted%20image%2020220306000029.png)

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

# Route 53
## What is the default DNS IP in VPC?
.02
if CIDR block is 172.10.0.0/16 then default DNS ip is 172.10.0.2
if CIDR block is 192.20.0.0/16 then default DNS ip is 192.20.0.2

## Why its named as Route 53?
the name resembles two things
- routing - load balancing the traffic globally
- 53 - DNS port

## ELB vs Route 53?
ELB is bound to a region where as Route 53 is global.

## What is difference between public and private hosted zones?
Private hosted zones are bound to one or more VPCs and can't be accessed publicly, where as public hosted doamin is accessible from internet.

## What are the default records you get when hosted zone is created?
NS - name server
SOA - start of authority

## Can I host example.com as public and private hosted zone? 
yes, same domain can be hosted as public and private.

## How can I check history of changes made to a hosted zone?
cloud trail

## What are different routing policies?
- simple - pointing to a single A record/IP address
- Geo
- weighted - point to multiple A records
- latency
- failover

## Can I use private DNS, if I dont want to use VPC?
No

## Can I use private hosted zones across regions?
yes
as long as the VPCs across the regions have connectivity.

## Can I configure backup site in case of failover?
yes

## How can I check health of an end point, if I dont know the IP address ?
based on the health checks performed by that other end point, i.e ELB

## Do I need internet connectivity to use private DNS?
No

## If my end point recovers, how does DNS failover reverse ?

## Can I set health check on URL, that redirects?
No

## What would happen if all health checks fails?

## How will I be notified, if my health checks fail?
Through, cloud watch alarms.

## Can I configure health check based on CPU, Memory,Disk usage or network usage?
Yes, you can use another health check as route 53 health check.

## What could be the end points for A record?
- IP address
- Cloud front distribution
- Elastic bean stack
- Amazon API gateway
- VPC endpoint
- ELB

## What type records, does AWS Route 53 support?
- A (address record)
- AAAA (IPv6 address record)
- CNAME (canonical name record) 
- CAA (certification authority authorization)
- MX (mail exchange record)
- NAPTR (name authority pointer record)
- NS (name server record)
- PTR (pointer record)
- SOA (start of authority record) 
- SPF (sender policy framework) 
- SRV (service locator) * TXT (text record)