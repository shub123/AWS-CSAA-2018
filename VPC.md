# VPC

- - - -
Virtual data center in cloud
Hardware von -  between the datacenter and vpc

Max 5 VPC in a Region * * * 
Layers of security -  vpn,security group, NACL
One internet gateway per VPC

EC2 - has both public/private IP addresses 
VPC peering- connect two different VPC s with direct networking. No transitive peering. * * * 
- - - -
 **CREATING VPC WILL CREATE** 
	Router
	Route table
	Network ACL
	Security Group

Subnet creation -selct vpc, AZ, ipv4 cidr, 
				5 ip address cannot be utilized as they r reserved 

Route table-
	Default- alll subnets in VPC are in the main route table 
	
To enable internet-
	Create a new route able, add route table record mapping 0.0.0.0/0 		with the internet gateway , associate the subnet, and auto assign public 	IP address * * * *  * *   

- - - -
**SUBNETS** -

Private -  cannot be accessed over internet
		no route tables associating the private subnet to the Internet gateway 

EC2 - > SUBNET/sec group  —> NACL ->  ROUTE TABLE —> INTERNET GATEWAY -> CLOUD 

Private subnet - needs patches , upgrades. To enable, use NAT * * * 

- - - -
NAT instance 
Create NAT instance in public subnet, disable source /dest checks, 
Route out from private subnet to the NAT instance 

Bottlenecks- increase 	instance size, 

- - - -

**NAT GATEWAY**
	More secure
   High availability, 
	Automatic public ip
	10 gbps
	advice- create gateways in different AZ 

- - - -

**NACLS** - 

ALLOWS all traffic
Can associate one subnet with only one ACL * * * 

IF NEW NACL - WILL DENYA L TRAFFIC BY DEFAULT  * * * 

Inbound rules/- outbound rules- stateless * * * 

RULES - EVALUATED IN NUMERICAL ORDER * * * 

Block IP addresses with NACLS, not security groups

- - - -

**LOAD BALANCERS AND CUSTOM VPCs**

 Atleast two AZones required for the Load balancer * * * * 

- - - -

**VPC FLOW LOGS-**

  Monitor traffic in.out thru vpc. In cloud watch
Can be created at 3 levels-  vpc, subnet, network interfaces level 

STEPS- vpc, flow log, role , new log group in cloud watch 

Cannot enable flow logs for peered VPC in different account   * * 
Cannot change flow log config once created
Nto all ip traffic logged * * 
	DNS< windows, DHCP  , metadata , 

- - - -
**NAT vs Bastions**

NAT enables internet access for ec2 instances in private subnets
Bastion server- allows administering EC2  in private subnets 

- - - -

VPC ENDPOINTS

Allows private ec2 instances to access resources (S3) without NAT .  * * * 

Vpc-  endpoint -> s3 gateway -> route table selection -> endpoint polices 

vpc endpoints - smimilar to NAT, but for accessing specific services

Gateways better than interfaces 

- - - -


