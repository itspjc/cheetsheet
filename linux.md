
- check disk size
  - `df -h`  
  - `du -h --max-depth=1`

- zip / unzip
  - compress
    - `tar -cvf T.tar files`
    - `zip -r <file.zip> <dir>`
  - expand
    - `tar -xvf T.tar (현재 디렉토리)`
    - `tar -xvf T.tar -C dir`
    - `unzip <file.zip> -d <dir>`
  
  
- SCP
  - `scp testfile2 root@192.168.159.129:/tmp/testclient`

    
    
### Users
- `adduser <username>` : add user
- `usermod -aG sudo <username>`: add group
- `newgrp <group-id>`: change current group ID during a login session.
    
### SSH Key
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

### Docker
- show docker container's stats
  - `docker ps -q | xargs  docker stats --no-stream`
  - `top -i`

## I can't umount nas
```bash
umount -f /nas
fuser -ck /nas
umount -l /nas  
```

## Modify client host in Windows
Path: `C:\Windows\System32\drivers\etc\hosts`
  


# Kubernetes

- When Auto completion doesn't work,

```bash
source /etc/bash_completion
```


# Redis
auth <password>
