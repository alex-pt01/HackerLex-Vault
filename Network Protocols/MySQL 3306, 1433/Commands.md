## Mysql connection

### Remote
```bash
mysql -u <username> -h <hostname> -P <port> -p
#specified hostname
#specified port

mysql -u <username> -h <hostname> -P <port> -p -D <database_name>
#specified database (-D)

select load_file("/etc/shadow");
```

### Local
```bash
mysql -u <username>
#specified username
#no password

mysql -u <username> -p
#with password

mysql -u <username> -p <database_name>
#specified database
```

