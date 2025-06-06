> Active Reconnaissance involves direct interaction with the target to obtain more detailed and accurate information.
Example: Scanning open ports with Nmap, enumerating SMB shares, or banner grabbing.

| Tool/Method     | Command/URL                           | Description                                        |
| --------------- | ------------------------------------- | -------------------------------------------------- |
| **Netcat (nc)** | `nc TARGET PORT`                      | Banner grabbing, raw TCP/UDP connections           |
| **Gobuster**    | `gobuster dir -u URL -w wordlist.txt` | Brute forcing directories and files on web servers |
| **Nikto**       | `nikto -h TARGET`                     | Web server vulnerability scanner                   |
| **Masscan**     | `masscan -p1-65535 TARGET`            | Very fast port scanner                             |
| **WhatWeb**     | `whatweb URL`                         | Web technology identification                      |
| **Wafw00f**     | `wafw00f DOMAIN`                      | Detect Web Application Firewalls                   |
 