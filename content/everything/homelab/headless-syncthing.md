---
title: Setting Syncthing on a Headless System
draft: false
tags:
  - homelab
---

# Setting Up SyncThing on a Headless Debian Rasp Pi
## Install SyncThing

1. Update the system
```bash
sudo apt update
sudo apt upgrade
```
2. Install `apt-transport-https` if it is not already installed
```bash
sudo apt install apt-transport-https
```
3. Install SyncThing's GPG Keys 
```bash
curl -s https://syncthing.net/release-key.txt | gpg --dearmor | sudo tee /usr/share/keyrings/syncthing-archive-keyring.gpg >/dev/null
```
4. Add the SyncThing's repo to the source list
```bash
echo "deb [signed-by=/usr/share/keyrings/syncthing-archive-keyring.gpg] https://apt.syncthing.net/ syncthing stable" | sudo tee /etc/apt/sources.list.d/syncthing.list
```
5. Update Sources List
```bash
sudo apt update
```
6. Install the SyncThing package
```bash
sudo apt install syncthing
```

## Allow External Connections to the Web Client
1. Run SyncThing to generate the config files
```bash
syncthing
```
2. Find where the config file is located
```bash
syncthing -paths
```
3. Modify the config file
	Change this line from `<address>127.0.0.1:8384</address>` to `<address>0.0.0.0:8384</address>`. This will allow connections from any address, if you want to restrict this to only allow connections from with the same subnet as the pi change the address to the pi's.
## Config SyncThing as a Service
1. Add the below content to the file `/lib/systemd/system/syncthing.service`
	- NOTE: CHANGE THE USER TO THE USER YOU WANT SYNCTHING TO RUN AS
```
[Unit] 
Description=Syncthing - Open Source Continuous File Synchronization 
Documentation=man:syncthing(1) 
After=network.target 

[Service] 
User=pi 
ExecStart=/usr/bin/syncthing -no-browser -no-restart -logflags=0 
Restart=on-failure 
RestartSec=5 
SuccessExitStatus=3 4 
RestartForceExitStatus=3 4 

# Hardening 
ProtectSystem=full 
PrivateTmp=true 
SystemCallArchitectures=native 
MemoryDenyWriteExecute=true 
NoNewPrivileges=true 

[Install] 
WantedBy=multi-user.target
```

2. Allow SyncThing to start at boot
```bash
sudo systemctl enable syncthing
```

3. Start SyncThing
```bash
sudo systemctl start syncthing
```

4. Access the web client at `https://<pie's ip>:8384`

# References
1. https://pimylifeup.com/raspberry-pi-syncthing/
2. https://forum.syncthing.net/t/help-finding-config-file-ubuntu-server/12465