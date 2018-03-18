# Docker Cheat Sheet
Documentation
* [OpenSource Container](https://shadow-soft.com/open-source-container-management-tools/)

```bash

```

## Table of Content
* Container Management
* Install Docker on Ubuntu 14.04 ++
* Docker Repository
* Docker Command
* 

## Container Management
ในตัวของ Docker เองก็มีตัวจัดการ Container ต่าง ๆ ที่เรียกว่า [Container Management](https://trial.docker.com/) ซึ่งจะอยู่ใน Docker EE เป็น Enterprise Edition โดยมีความสามารถหลัก ๆ ดังนี้
* สามารถบริหารจัดการ Container และ Resource ทั้งหมดได้จากหน้า Web UI
* ด้วยความที่เป็น UI ทำให้เราไม่จำเป็นต้องรู้คำสั่งต่าง ๆ ใน Docker
* สามารถกำหนด Role Based Access Control (RBAC)
* End-to-End Security Model และสามารถปรับแก้ไขได้แบบ Dynamic
* สามารถใช้งานร่วมกับ LDAP/AD

นอกจากนี้ยังมี Service Provider ที่ให้บริการ Container อีกมากมาย ทั้งที่ฟรีและไม่ฟรี เช่น
* [kontena](https://kontena.io/) opensource
* [portainer](https://portainer.io/)

## Install Docker on Ubuntu 14.04 ++
```bash
$ sudo su -
# apt-get update
# apt-get install docker.io
```

## Docker Repository
* [rabiitmq](https://hub.docker.com/_/rabbitmq/)
* [elasticsearch](https://hub.docker.com/_/elasticsearch/)
* [kibana](https://hub.docker.com/_/kibana/)
* [consul](https://hub.docker.com/_/consul/)
* [node](https://hub.docker.com/_/node/)
* [nginx](https://hub.docker.com/_/nginx/)
* [redis]()
* [memcached](https://hub.docker.com/_/memcached/)
* [ispconfig](https://hub.docker.com/r/jerob/docker-ispconfig/)
* [ubuntu]()
* [snipit](https://hub.docker.com/r/snipe/snipe-it/)
* [busybox](https://hub.docker.com/_/busybox/)

## Docker Image
* Docker Pull Image
```bash
$ docker pull cloudera/quickstart:latest
```

* Docker Show Image
```bash
$ docker images -a
```

* Docker Remove Image
```bash
$ docker rmi [image_name]
```

* Docker Tag Image
```bash
$ docker tag latest latest:2018
```

## Docker Container
* Docker Run Container
```bash
$ docker run -v /root:/mnt --hostname=quickstart.cloudera --privileged=true -it -p 9092:9092 -p 2181:2181 -p 11122:11122 -p 8080:8080 -p 8440:8440 -p 8441:8441 cloudera/quickstart /usr/bin/docker-quickstart

--volume -v [host_directory]:[docker_directory]
```

* Docker Show Container
```bash
$ docker ps
$ docker ps -a
```

* Docker Stop Container
```bash
$ docker stop [container_id]
```

* Docker Restart Container
```bash
$ docker restart [container_id]
```

* Docker Remove Container
```bash
$ docker rm [container_id]
```

* Docker Exec Container
```bash
$ docker exec -it [container_id] bash 
```

* Docker Expose Port
```bash
$ docker inspect [container_id]
```

* Docker History
```bash
$ docker history
```

* Docker Rename
```bash
$ docker rename [container_name] [container_newname]
```

* Docker Rename Repository
```bash
$ docker tag [repository_name]:[tag] [repository_newname]:[tag]
```

## Docker Hub
* Docker Login
```bash
$ docker login -u [username] -p [password]
```

* Docker Login Status
```bash
$ cat ~/.docker/config.json
```

* Docker Commit
```bash
$ docker commit [container_id] [image_name]
```

## Dockerfile
* Docker Create from Dockerfile
```bash
$ docker build -t [image_name] [dockerfile_path]
```

* Docker Save Image
```bash
$ docker save busybox > busybox.tar
```

* Docker View Size
```bash
$ ls -sh busybox.tar
```

## Docker Network
* Docker iptables
```bash
$ iptables -t nat -A DOCKER -p tcp --dport [localhost_port] -j DNAT --to-destination [container_port]:[port]
https://fralef.me/docker-and-iptables.html
```

## Credit
https://docs.docker.com/install/linux/docker-ce/ubuntu/#upgrade-docker-after-using-the-convenience-script