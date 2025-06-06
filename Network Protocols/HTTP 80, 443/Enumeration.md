
```bash
http $IP
curl http://IP/ | more
wget "http://IO/index"  //Download 
lynx http://IP
```

## Directories
```bash
gobuster dir -u ftp://<target-ip> -w <wordlist-path>
dirb http://IP
```

### Nmap

> Nmap
```bash
sudo nmap -p80 -sV -O IP
```

> Location Nmap scripts
```bash
ls -la /usr/share/nmap/scripts | grep -e "http"

nmap IP -sV -p80 --script http-enum
nmap IP -sV -p80 --script http-headers
```

> Use browsh when we don’t have a browser

```bash
browsh --startup-url http://IP/Default.aspx
```

### Enumeration with Metasploit

```bash
msfconsole
search type:auxiliary name:http

use auxiliary/scanner/http/robots_txt
use auxiliary/scanner/http/http_version
use auxiliary/scanner/http/http_header 
use auxiliary/scanner/http/apache_userdir_enum
use auxiliary/scanner/http/http_login
```

### Exploitation
```bash
use auxiliary/scanner/http/brute_dirs
use auxiliary/scanner/http/dir_scanner
use auxiliary/scanner/http/files_dir
use auxiliary/scanner/http/dir_listing
use auxiliary/scanner/http/http_put
```


### Webdav
```bash
nmap IP -sV -p80 --script http-webdav-scan --script-args http-methods.url-path=/webdav/
nmap IP -sV -p80 --script http-methods --script-args http-methods.url-path=/webdav/
```

### Shellshock - gettime.cgi
```bash
http://IP/gettime.cgi

nmap -sV -p 80 --script=http-shellshock --script-args "http-shellshock.uri=/gettime.cgi" IP

use exploit/multi/http/apache_mod_cgi_bash_env_exec
```
