### Connect with Terminal
```bash
ssh username@X.X.X.X
ssh -i path/to/private_key user@target-ip
```

### Notes
> If hydra is not working because of the auth method that SSH is using
```bash
sudo mousepad /etc/ssh/ssh_config
```

> Add
```bash
Host *
  Ciphers +3des-cbc,aes128-cbc,aes192-cbc,aes256-cbc
  KexAlgorithms +diffie-hellman-group-exchange-sha1,diffie-hellman-group1-sha1,diffie-hellman-group14-sha1
  HostKeyAlgorithms +ssh-rsa,ssh-rsa-cert-v01@openssh.com,ssh-dss,ssh-dss-cert-v01@openssh.com
  PubkeyAcceptedAlgorithms +ssh-rsa,ssh-rsa-cert-v01@openssh.com,ssh-dss,ssh-dss-cert-v01@openssh.com  
```