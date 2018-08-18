# APPLICATION SERVICES

- - - -
**SQS**

Simple queue service 
Fifo
ASYNC PROCESSING , distributed , PULL based
Command ec2 instances will poll sql to get jobs and process ondemand (autoscaling) * * 
Upto 256 kb ,
messages can be retrieved with SQS api 

If producer rate> consumer rate -> promotes sys stability 
if intermittent connectivity with system , on demand processing 

ALSO, autoscaling0 based on message rate * * 

STANDARD QUEUES -
	Not strictly FIFO, Could have duplicated messages
	AWS does best effort ordering
	nearly unlimited capacity

FIFO QUEUES-
	Strictly FIFO, unique messages 
	300 transactions/sec -> not unlimited

Retention -> 1 min to 14 days. , default is 4 days 
Visibility timeout -> 
	default is 30 secs
	max is 12 hours 
 
Long/short polling -> Long polling is cost effetctive

- - - -
**SWF**

Enable creation of workflow processes 

Workflow starter-
	 Initiates the workflow

Workers
	get tasks fro SWF , process and return results

Decider-
	controls task coordination ,

Decider <-> SWF <->Workers 

TASK will not be duplicated * * * 

State maintained by SWF
Decider, workers- stateless, can be scaled quickly

SWF domains- 	container for all tasks , execution flows etc

registerDomain- IN JSON  * 

Workflow - max 1 year retained  * * * 

Task oriented vs Message oriented (SQS) * * * 
 Never duplicated vs duplicated (SQS)
Keeps track of all tasks 

- - - -
**SNS**

PUB SUB 
Push model  *  * 
Separate producer from consumer 

To mobile, sms, email, lambda , http endpoints    

Topics- group recipients 
	stored across multiple AZ 

SNS, Create topic, subscribers, publish message 

Easy integration, multiple protocols 	

- - - -
**Elastic Transcoder**

Convert media
- - - -

API GATEWAY

API Cache- TTL 
Integration with Lambda, other endpoints 
CORS
- - - -
**Kinesis**

Streaming data processor *. * 
Streams, firehose, analytics

Producer (ec2, not, mobile,) -> Shards (7 day retention) -> Consumers (ec2) 

Streams - has multiple shards
Firehose -  cannot be retained. AUTOMATED , NO SHARDS * * * 
			integration with Lambda for automated analysis of data

Analytics-  enable sql queries on streams , Firehose

- - - -
**EXAM TIPS**








