---
title: appointment
draft: false
tags:
  - hackthebox
---
1. What does the acronym SQL stand for? 
Structured Query Language
2. What is one of the most common type of SQL vulnerabilities? 
sql injection
3. What is the 2021 OWASP Top 10 classification for this vulnerability?
A03:2021-Injection 
4. What does Nmap report as the service and version that are running on port 80 of the target? 
`Apache httpd 2.4.38 ((Debian))`

`nmap -sV 10.129.16.120`

5. What is the standard port used for the HTTPS protocol?
443
6.  What is a folder called in web-application terminology? 
directory
7. What is the HTTP response code is given for 'Not Found' errors? 
404
8. Gobuster is one tool used to brute force directories on a webserver. What switch do we use with Gobuster to specify we're looking to discover directories, and not subdomains? 
dir
9. What single character can be used to comment out the rest of a line in MySQL? 
\#
10. If user input is not handled carefully, it could be interpreted as a comment. Use a comment to login as admin without knowing the password. What is the first word on the webpage returned?
it can't just be admin \# because we need to close the area where admin is entered

username: admin '#
password: \<anything>
