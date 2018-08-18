# Best practices
**Scaling**
	Proactive cycling scaling
	Proactive event based scaling
	Auto scaling- based on metrics

Decoupling
Elasticity

SECURITY-
	Web Server-  22,80
	App server- only 22 from certain machines
	DB server = accessible only by app server
- - - -
**Well Architected framework**

 **Security**
	all layers, traceability, best practices, 
	Shared responsibility - c	ustomer + aws 
	Data protection, Privilege, Infra protection, Detective controls ,encryption 
	11 9s of durability
	versioning
	Privilege  management  - Roles, ACLs , Groups 
	INFRA PROTECTION- vpc, nacl, routing, private subnets, 
		private subnets , host boundaries with roles,, sec groups etc 
	Detective controls - cloud trail, clod watch, aws config, s3 , glacier 	

**Reliability**
	ability to recover/scale
	test recovery procedures, simian 
	recover from failure- thru automated monitoring,  recovery , trigger
	scaling ,redundancy 
	Foundations - take care of comms, basics, service limits, 
		Tech managers, topology of NW 
	Change management - automate Changes, adapt ,  how CM done 
	Failure management - monitor, react, plan 
		FAILOVER, Autoscaling , Multi AZ, Snapshots, CRR , Archival , CF 

 **Efficiency**
	efficient allocation of resources vs demand Changes 
	Serverless, bootstrap in minutes,  pay per usage * * 
	Compute
		choose server by cpy/ram optimized type; 
, storage
	storage choice by type, update freq, 
, database , 

space-time tradeoff
		reducee latency 
	
**Cost Optimization**
		minimal cost- serverlerss. * *. 
**Operational Excellence** 

Planning, operation, response 


- - - -

