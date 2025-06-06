
### nmblookup
```bash
nmblookup -A IP
nmblookup -A $IP
nmblookup -L $IP -N 
```

### smbclient
```bash
smbclient -L IP -N
smbclient -L IP -U USERNAME 
smbclient //IP/anonymous -N
smbclient -L //IP -U anonymous
```
> Anonymous connection is allowed since **shares are displayed without requirement of password.**

### rpcclient
```bash
rpcclient -U "" -N IP
```

### enum4linux
```bash
enum4linux -o $IP
enum4linux -o $IP
enum4linux -G $IP   //groups
enum4linux -S $IP   //shares
enum4linux -r -u "USERNAME" -p "PASSWORD" $IP 
```

### smbmap
```bash
smbmap -H IP -u USERNAME -p PASS
smbmap -u USERNAME -p "" -d . -H $IP
smbmap -H $IP -u USERNAME -p "PASSWORD" -x 'ipconfig'
smbmap -H $IP -u USERNAME -p "PASSWORD" -r 'C$'
smbmap -H $IP -u USERNAME -p "PASSWORD" -L

smbmap -H $IP -u USERNAME -p "PASSWORD" --upload 'file_location/backdoor' 'C$\backdoor'
smbmap -H $IP -u USERNAME -p "PASSWORD" --download 'C$\FILE'
```

### Nmap

> Nmap
```bash
nmap -sV -sC -Pn -A -T4 -p21 IP
```

> Location Nmap scripts
```bash
ls -la /usr/share/nmap/scripts | grep -e "smb"
```

> Nmap Script  

**export IP=xxx**

```bash
nmap --script=smb-os-discovery -p 445 $IP
nmap -p445 --script smb-protocols $IP
nmap --script smb-enum-users.nse -p445 IP
nmap -p445 --script smb-enum-shares IP

nmap -p445 --script smb-enum-users,smb-ls --script-args smbusername=USERNAME,smbpassword=PASSWORD IP
nmap -p445 --script smb-domains --script-args smbusername=USERNAME,smbpassword=PASSWORD IP
nmap -p445 --script smb-enum-groups --script-args smbusername=USERNAME,smbpassword=PASSWORD IP
nmap -p445 --script smb-enum-services --script-args smbusername=USERNAME,smbpassword=PASSWORD IP
```

### Enumeration with Metasploit

```bash
msfconsole
search type:auxiliary name:smb

use auxiliary/scanner/smb/smb_version 
use auxiliary/scanner/smb/smb2 
use auxiliary/scanner/smb/smb_enumusers 
use auxiliary/scanner/smb/smb_enumshares
use auxiliary/scanner/smb/pipe_auditor
```

