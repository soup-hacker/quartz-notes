---
title: redeemer
draft: false
tags:
  - hackthebox
---
 
1. Which TCP port is open on the machine? 
6379

2. Which service is running on the port that is open on the machine? 
redis

3. What type of database is Redis? Choose from the following options: (i) In-memory Database, (ii) Traditional Database 
In-memory Database

4. Which command-line utility is used to interact with the Redis server? Enter the program name you would enter into the terminal without any arguments.
`redis-cli`
5. Which flag is used with the Redis command-line utility to specify the hostname? 
`-h`

`redis-cli -h <host> -p <port> -a <password>`
6. Once connected to a Redis server, which command is used to obtain the information and statistics about the Redis server? 
`info`

7. What is the version of the Redis server being used on the target machine? 
`5.0.7`

from `info` output

8. Which command is used to select the desired database in Redis? 
`select 0`

from info output we can see that there is only 1 database with an index of `0`.

9. How many keys are present inside the database with index 0? 
4

10. Which command is used to obtain all the keys in a database? 
`keys *`