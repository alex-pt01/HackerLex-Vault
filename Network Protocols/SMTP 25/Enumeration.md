
### Banner Grabbing
```bash
nmap -sV -script banner IP
```

### Fetch the username
```bash
nc IP 25
```

> Check if `admin` and `commander` user exists
```bash
nc IP 25

VRFY admin@openmailbox.xyz
	252 2.0.0 admin@openmailbox.xyz   // YES admin exists

VRFY commander@openmailbox.xyz
	550 5.1.1 <commander@openmailbox.xyz>: Recipient address rejected: User unknown in local recipient table
# No "commander" doesn't exist
```

### Nmap

> Nmap
```bash
sudo nmap -p25 -sV -sC -O IP
```

> Location Nmap scripts
```bash
ls -la /usr/share/nmap/scripts | grep -e "smtp"

nmap -p25 --script smtp-enum-users.nse DOMAIN
```

### Enumeration with Metasploit

```bash
msfconsole
search type:auxiliary name:smtp
use auxiliary/scanner/smtp/smtp_enum
use auxiliary/scanner/smtp/smtp_version
```

