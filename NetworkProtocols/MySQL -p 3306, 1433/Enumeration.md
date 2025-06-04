

### Banner Grabbing
```bash
nc -nv IP 3306
```

### Nmap

> Nmap
```bash
nmap -sV -sC -Pn -A -T4 -p3306 IP
```

> Location Nmap scripts
```bash
ls -la /usr/share/nmap/scripts | grep -e "mysql"
```
> Nmap Script  

```bash
nmap $IP -sV -p3306 --script=mysql-empty-password
nmap $IP -sV -p3306 --script=mysql-info
nmap $IP -sV -p3306 --script=mysql-users --script-args="mysqluser='root',mysqlpass=''"
nmap $IP -sV -p3306 --script=mysql-databases --script-args="mysqluser='root',mysqlpass=''"
nmap $IP -sV -p3306 --script=mysql-variables --script-args="mysqluser='root',mysqlpass=''"
nmap --script=mysql-audit --script-args="mysql-audit.username='root',mysql-audit.password='',mysql-audit.filename=''" -p3306 IP
nmap $IP -sV -p3306 --script=mysql-dump-hashes --script-args="username='root',password=''"
nmap $IP -sV -p3306 --script=mysql-dump-hashes --script-args="quer='select count(*) from books.autors;'username='root',password=''"
```

### Enumeration with Metasploit

```bash
msfconsole
search type:auxiliary name:mysql

use auxiliary/scanner/portscan/tcp
use auxiliary/scanner/mysql/mysql_file_enum
use auxiliary/scanner/mysql/mysql_hashdump
use auxiliary/admin/mssql/mssql_enum
use auxiliary/admin/mssql/mssql_enum_sql_logins
use auxiliary/admin/mssql/mysql_exec
use use auxiliary/admin/mssql/mysql_enum_domain_accounts
use auxiliary/scanner/mysql/mysql_schemadump
use auxiliary/scanner/mysql/mysql_writable_dirs
```

