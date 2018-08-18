# ROUTE 53 

**DNS 101** 

Similar to phonebook
Domain —> IP address translation using records 
Ipv4,v6. 

Ipv4- 32bit, ipv6-128 bits
TLDS - gooegle.com , 
Second level domain names - co.uk
 
IANA - manages the TLD domains .  Which will. Periodically created new tlds

Domain registrars write DNS records, DNS servers query the dns records !

SOA- info on owner of domain , MAX TTL 
NS -  USED by TLD server to route to content dns servers for authoritative 
A record- fundamental, maps a Domain name to an IP address 

TTL - time until which the DNS record is cached in users machine 
Cname-  canonical name- can’t be used for naked domains 
Alias - map resource sets  to elb, cf dist , s3 buckets etc

Always use Alias records instead of c name
- - - -
#   *Routing Policies*  

#SImple

to one region

#weighted

    % to different regions - 
   Create Alias (weitghted)  for dffenrt elb In different regions and set weights (max 255)

#latency

Based on approx latency
DNS queries on Alias - latency records and figure out optimal routing region by latency 

#failover

Active/passive setup
R53 does heath checks on nodes
If health check fails - routed  to passive site 

Create health check config in r53 and map to primary instance 

#geolocation

Based on geo location of end user
MAP specific locations to a specific regional endpoint

DEFAULT- catch all, 

- - - -
**EXAM TIPS**

Cannot have public IP address for an ELB  * 
MX records
50 domain names max 
