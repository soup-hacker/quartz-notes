---
title: dancing
draft: false
tags:
  - hackthebox
---

# Task 1 - What does the 3-letter acronym SMB stand for? 
sever message block

# Task 2 - What port does SMB use to operate at? 
445

# Task 3 - What is the service name for port 445 that came up in our Nmap scan?
`microsoft-ds`
`nmap -sV 10.129.25.224`

# Task 4 - What is the 'flag' or 'switch' that we can use with the smbclient utility to 'list' the available shares on Dancing? 
`smbclient -L 10.129.25.224`

# Task 5 - How many shares are there on Dancing? 
`smbclient \\\\10.129.25.224\\WorkShares`

# Task 6 - What is the name of the share we are able to access in the end with a blank password? 
WorkShares 

# Task 7 - What is the command we can use within the SMB shell to download the files we find?
`get`

