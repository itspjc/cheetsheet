
- check disk size
  - `df -h`
  - `du -h --max-depth=1`

- compress, zip
    - compress: `tar -cvf T.tar files`
    - `zip -r <file.zip> <dir>`
- expand, unzip
    - `tar -xvf T.tar (현재 디렉토리)`
    - `tar -xvf T.tar -C dir`
    - `unzip <file.zip> -d <dir>`
  
- SCP
  - `scp testfile2 root@192.168.159.129:/tmp/testclient`

### Ports
`netstat -ntlp | grep :<port>

    
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

- remove unnecessary docker containers
  - `docker rmi -f $(docker images | grep "gcr.io" | awk "{print \$3}")`
  - `sudo docker system prune -a -f`
  - `docker run --detach --name [container_name] -p 80:80 [repo_name]`

- backup docker images
```
IDS=$(docker images | awk '{if ($1 ~ /^(debian|centos)/) print $3}')
docker save $IDS -o /path/to/save/somedockersimages.tar
```

### Docker Compose
- See all logs of running containers described in docker-compose yaml files: `docker-compose -f run.yml logs --tail=0 --follow`

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
`auth <password>`
redis-cli -h 10.146.0.11 -p 6379 -a p@ssword1
KEYS **
GET <KEY>
  
### PM2
```
pm2 start --name dashboard npm -- start
pm2 start --name frontend-gui npm -- start --watch
```


### gcloud
```
gcloud auth login --no-launch-browser
gcloud config set project lge-pri-cloud

gcloud auth login
gcloud auth configure-docker
```

