---
title: sequel
draft: false
tags:
  - example-tag
---
 
1. During our scan, which port do we find serving MySQL? 
3306 

`nmap -sV 10.129.166.75`
2. What community-developed MySQL version is the target running?
MariaDB

`nmap -A 10.129.166.75`
3. When using the MySQL command line client, what switch do we need to use in order to specify a login username? 
`-u`

````sql
mysql -u USERNAME -pPASSWORD -h HOSTNAMEORIP
````

4. Which username allows us to log into this MariaDB instance without providing a password?
`root`

5. In SQL, what symbol can we use to specify within the query that we want to display everything inside a table? 
`*`

`show databases;` -> display all databases
`use <database name>;` -> select a database
`show tables;` -> show all tables in a database
`select * from <table name>;` -> return everything within a table

6. In SQL, what symbol do we need to end each query with?
`;`

7. There are three databases in this MySQL instance that are common across all MySQL instances. What is the name of the fourth that's unique to this host? 
`htb`