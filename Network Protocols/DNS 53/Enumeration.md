
### Banner Grabbing
```bash
# Use dig to determine DNS server versions
dig version.bind CHAOS TXT @DNS

nmap --script dns-nsid <DNS_IP>

nc -nv -u <DNS_IP> 53
```

### DNS Enumeration Using Online Tools
```bash
dnsdumpster.com 
dnsrecon.com
spyse.com
securitytrails.com
dnslytics.com
```

### DNS Enumeration with Google Dorks
```bash
site:hackviser.com -www.hackviser.com -site:www.hackviser.com
maltego
```

### Subdomain discovery
```bash
dnsenum --dnsserver <DNS_IP> --enum -p 0 -s 0 -o subdomains.txt -f <WORDLIST> <DOMAIN>
```

### Dig
```bash
dig <DOMAIN>

dig A <DOMAIN>

dig -x <IP_ADDRESS>

dig @<DNS_SERVER_IP> <DOMAIN>

dig any <DOMAIN> @<DNS_IP>

dig NS <target-domain>
```

### nslookup
```bash
nslookup <DOMAIN>

nslookup -type=MX <DOMAIN>

nslookup <DOMAIN> <DNS_IP>

nslookup -type=NS <target-domain>
```

### Nmap
> Nmap
```bash
nmap -sV -sC -Pn -A -T4 -p21 IP
```

> Location Nmap scripts
```bash
ls -la /usr/share/nmap/scripts | grep -e "dns"
```

> Nmap Script  

**export IP=xxx**

```bash
nmap -n --script "(default and *dns*) or fcrdns or dns-srv-enum or dns-random-txid or dns-random-srcport" <IP>
```

### Enumeration with Metasploit

```bash
msfconsole
search type:auxiliary name:dns

use auxiliary/gather/enum_dns
```

