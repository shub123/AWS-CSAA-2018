# EXAM TIPS 

Cross account  management - login into inter linked accounts 

**Vpc peering**

	no overlapping cider blocks
	no vpc peering thru transitive * * 

**Direct Connect**

**Security Token Service** 
	temp acess
	ACTIVE dir. - SAML 
	OpenID -fb, goog 
	cross account access 
	
   User -> Identity Broker -> LDAP
			-> STS -> token

Token -> s3 

**Active directory** 
	
**Workspaces**
	Persistent, VDI to windows
	Acitive diretory/AWS credntialed 	 
	Windows 2008 R2 server
	data in D: drive is backed up every 12 hours 

**ECS** 
	Docker
	Virtualization - full sized OS +apps
	Containers- apps + small layer of OS 

 	Layered - image has multiple layers 
	Dockerfile=. image build from instructions set . Dockerfile contains the instructions 
	
	Task Definiition. -  used to describe tasks running on ECS 