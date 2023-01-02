Install SSH
```bash
sudo apt install ssh
```

Start / check status of SSH service
```bash
sudo systemctl start ssh
sudo systemctl status ssh
```

Login to SSH
```bash
ssh server@192.168.0.100
```

Login with key
```bash
ssh server@192.168.0.100 -i id_rsa
```
***

## Generate SSH Key

```bash
ajai@ubuntu: ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/home/kali/.ssh/id_rsa):
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/kali/.ssh/id_rsa
Your public key has been saved in /home/kali/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:pIgRf21NfrqZbpIlvAhX+iwI/XPBkmRLEUYPhBEUc0k kali@kali
The key's randomart image is:
+---[RSA 3072]----+
|  ..*OEo  .      |
|   o.+o+ +       |
|  . . ..= o .    |
|   o o++.  o     |
|  ...+.BS .      |
|  . o * = .+     |
|   . = = *+      |
|    . = B..      |
|       + o.      |
+----[SHA256]-----+
```
1. Use **ssh-keygen** command
2. Provide directory to save the private adn public key, leave blank for default directory
3. Provide password for the key, leave blank for no password

## Connect to server using private key

1. Add SSH public key to server
- ssh-copy-id
```bash
ssh-copy-id -i ~/.ssh/id_rsa.pub server@192.168.0.100
```
- scp
```bash
scp /home/client/.ssh/id_rsa.pub server@192.168.0.100:/home/server/.ssh/authorized_key
```

## SSH Configuration

We can change configuration at /etc/ssh/sshd_config

What can change:
- Listen port / address
- Logging
- Password Authentication

**NOTE**
For some reason, if you want to ssh using your own private key, you need to add your own public key on your own authorized key. :D
