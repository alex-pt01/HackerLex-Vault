## 🔐 SSH Scripts with Nmap

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
