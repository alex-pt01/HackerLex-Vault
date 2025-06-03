## 🔐 SSH Scripts with Nmap

> Location of SSH-related Nmap scripts
```bash
ls /usr/share/nmap/scripts/*ssh*.nse
```


> Retrieves and displays the SSH host's public key.
```bash
nmap -p 22 --script ssh-hostkey <IP>
```

> Lists the supported SSH authentication methods.
```bash
nmap -p 22 --script ssh-auth-methods <IP>
```

> Attempts brute-force password guessing against the SSH service.
```bash
nmap -p 22 --script ssh-brute <IP>
```

> Checks if a given public key is accepted by the SSH server.
```bash
nmap -p 22 --script ssh-publickey-acceptance <IP>
```

> Enumerates the encryption and authentication algorithms supported by the SSH server.
```bash
nmap -p 22 --script ssh2-enum-algos <IP>
```

> Detects whether the SSH server supports the outdated and insecure SSHv1 protocol.
```bash
nmap -p 22 --script sshv1 <IP>
```

> Logs in via SSH (if credentials are valid) and runs the specified command on the remote system.
```bash
nmap -p 22 --script ssh-run --script-args="user=root,pass=toor,command=uname -a" <IP>
```
