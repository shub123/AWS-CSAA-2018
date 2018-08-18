# CREATE FAULT TOLERANT WORDPRESS SITE
**Flow diagram** 
Client -> R53 -> ALB -> web server -> RDS
			           		  ->  S3 code 
				  		  -> S3 media assets (via cloud front) 

**Implementation**
1. 	Security groups-  
		Web server,- 80 ,22
		RDS instances - 3306  inbound from web server SG 

2. RDS
	   Mysql -Prod (Multi AZ)
	   RDS sec group, no public ip * * * 
	  set db name, username, 

3. S3 bucket
	   S3 for code, media
	  IAM roles for Ec2 -> S3 access

4. Cloud Front
	    with origin as s3 media bucket
	    disable access to S3 media bucket 

5. EC2 web server 
	user data, keypair, ec2 sec group
	Configure Wordpress , db config 

6. Images
	Move images from wp-content to s3 images bucket
	url rewrite- .htaccess -> 
	_etc_httpd/conf -> edit  httpd.conf file -> AllowOverride All 

7. App Load Balancer
	target group,  target, health checks 
8. . Route53 *
	map to the ELB 
	Add alias-normal routing 	   

9. Autoscaling group

	one ec2 instance willl be used to write posts to s3 
		_etc -> nano crontab ->  aws s3 sync —delete /var_www_html  s3:_/ 1 
		       ->  aws s3 sync —delete _var_www_html /wp-content  s3:_/ 2

	autoscaling ec2 instance will retrieve posts from s3 
		_etc -> nano crontab ->  aws s3 sync —delete s3:_/  _var_www/html 
		create an AMI from this instance
		Launch config
		Autoscaling config
		ALB attach 
		Update R53 A record to map to this ALB 
	
	
10. **CLOUDFORMATION**
	Templates 
	 Saves time
	 New stack from an existing template
	
		