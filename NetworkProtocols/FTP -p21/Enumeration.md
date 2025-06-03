
## Banner Grabbing
```bash
nc -nv X.X.X.X 21
```

## Directories
```bash
gobuster dir -u ftp://<target-ip> -w <wordlist-path>

```

### Nmap

> Nmap
```bash
nmap -sV -sC -Pn -A -T4 -p21 IP
```

> Location Nmap scripts
```bash
ls -la /usr/share/nmap/scripts | grep -e "ftp"
```

> Nmap Script  

**export IP=xxx**

```bash
nmap -p 21 --script ftp-anon $IP
nmap -p 21 --script ftp-features $IP
nmap --script "ftp*" -p 21 $IP


```

### Enumeration with Metasploit

```bash
msfconsole
search type:auxiliary name:ftp

use auxiliary/scanner/ftp/anonymous
use auxiliary/scanner/ftp/ftp_version
use auxiliary/scanner/portscan/tcp 
use auxiliary/scanner/ftp/ftp_bounce

```

