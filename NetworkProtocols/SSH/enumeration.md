### Banner Grabbing & Audit
```bash
nc -vn $IP 22
ssh-audit $IP 22
```
### 🔐 SSH  with Nmap

> Nmap
```bash
nmap -sV -p 22 IP
```

> Location of SSH-related Nmap scripts
```bash
ls /usr/share/nmap/scripts/*ssh*.nse
```

> Nmap Script  

**export IP=xxx**

```bash
nmap -p 22 --script ssh-hostkey $IP
nmap -p 22 --script ssh-auth-methods $IP
nmap -p 22 --script ssh-brute $IP
nmap -p 22 --script ssh-publickey-acceptance <IP>
nmap -p 22 --script ssh2-enum-algos $IP
nmap -p 22 --script sshv1 $IP
nmap -p 22 --script ssh-run --script-args="user=root,pass=toor,command=uname -a" $IP
```

### SSH Enumeration with Metasploit

```bash
msfconsole
search type:auxiliary name:ssh

use auxiliary/scanner/ssh/ssh_version
use auxiliary/scanner/ssh/ssh_login
use auxiliary/scanner/ssh/ssh_enumusers
use auxiliary/scanner/ssh/libssh_auth_bypass
```

