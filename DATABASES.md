# DATABASES 

- - - -
**DB 101**

RDB, non relational , etc 
Rdb-  1970s - tables, rows , columns 
Excel- file with db management 
mysqL, AURORA,. SQL server, oracle , postgres, mariadb. - supported in AWS

NON RELATIONAL -  collection -> document -> kvpairs
	dynamodb, 
	json format 

DATA warehousing - 
	large data bI, queries
 	OLTP -  	online txn processing - ex online orders
	OLAP -  query, analyst large volumes of data , different architecture —> 		REdSHIFT amazon 

Elasticache- 
	in memory caches
	memcached, redis

- - - -

**RDS_MYSQL**
Inbound -  3306.  To allow ec2 to communicate to mysql, map ec2 sec grp to the RDS inbound port 3306

MAX SIZE-  16 TB. * * * 
Automated backups-
	default
	daily snapshot
	retention - 35 days 
	If rds instance deleted- all backups cleared

Snapshots-  	
	manually
	if RDS deleted, snapshots are still retained

Restore backups-
	
Muti AZ	
	sync replication to another AZ within same region
	only for Disaster recovery - failover

Read Replicas 
	Performance improvement enabling
	balance db traffic 
	RR  - can be in another AZ. Or a different regionn * 
	Async repilication
	not available for Oracle/SQL server
	Upto 5 RR , RR of RR
	need automatic backups turned ON 
	RR + MULTI AZ- good practice
	RR can be 	promoted to be an independent DB. Will break replication

- - - -
**AMAZON AURORA** 

	AMZ developed
	5 X perf of Mysql, for 10% f the cost 
	Competitor for Oracle
	Simplicity  + Scalability of Professional Databases 

Scaling -	
	>= 10gb , 10gb incrmenet,s upto 64TB
	Compute upto 32 cpus, 244 gb rAM
	2 copies of data in each AZ* 3 AZ.  = 6 copies
	
Durabiliy 
	Can lose 2 copies and still have write 
	Can lose 3 copies and still have read capability 
	Self healing- if any corruption is corrected automatically

REPLICAS-
	Aurora replicas = 15 
	Mysql read replicas- 5 
	
Read replicas- with reader access - set tiered priority 
Automatic failure from primary cluster to aurora replica cluster 

- - - -
**DYNAMO DB** 

NO SQL db 
Amazon developed
Both document and KV data models
SSD
3 AZ - 

Eventual  consistency -
	change will be available in few secs

Strongly consistent-
	imediatyel available data 

Read/Write capacity units

	expensive writes, cheap reads

Reserved capacity - buy upfront, like reserved ec2 instances * 

Easier to scale - ++ capacity units  * * * 

- - - -
**DATA WARHOUSE**

$0.25 /PETABYTE 

Single (160gb) /muti node config

	Leader node- manages client interfacing
	Comptute node- does compute (upto 128) 

Columnar data- organized by column values -> much less IO, 
Advanced compression -    AMZ automatically optimizes the compression method, based on nature of data, 
Massively parallel processing- distributes dynamically to nodes available 

Cost=. node_hours + Backup + data transfer 

Security:
	Encrypted in rest(AES 256) /transit (SSL)

Only one AZ !!! * 

Restore snapshots to another AZ—

- - - -
**Elasticache** 


Redis, Memcached
In memory cache in cloud
Freq used data is cached -> lead to much improved perf for freq accessed data/ results of intensive computation can be cached 

Memcached- 
	No Master /slave replication and Multi AZ
	
Redis - 
	OS KV store, supports sorted sets/list	
	      Master /slave replication and Multi AZ

- - - -
**Exam Tips**

	
Reduce stress- 
	use elastic ache (if read heavy)
	/ Red shift(if OLAP heavy )
