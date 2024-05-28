---
title: meow
draft: false
tags:
  - hackthebox
---
 
# Task 1 - What does the acronym VM stand for?
Virtual Machine

# Task 2 - What tool do we use to interact with the operating system in order to issue commands via the command line, such as the one to start our VPN connection? It's also known as a console or shell. 
Terminal

# Task 3 - What service do we use to form our VPN connection into HTB labs? 
openvpn

# Task 4 -  What tool do we use to test our connection to the target with an ICMP echo request?
ping
`ping 10.129.195.191`
# Task 5 - What is the name of the most common tool for finding open ports on a target? 
nmap
`nmap -sV 10.129.195.191`
# Task 6 -  What service do we identify on port 23/tcp during our scans? 
telnet
`telnet -l root 10.129.195.191`
# Task 7 - What username is able to log into the target over telnet with a blank password? 
root
