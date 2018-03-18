## Git Server Docker

* Pull
```bash
$ docker pull jkarlos/git-server-docker
```

* Run
```bash
$ docker run -d -p 222:22 -p 280:80 -p 2443:443 -v ~/git-server/keys:/git-server/keys -v ~/git-server/repos:/git-server/repos jkarlos/git-server-docker 
```

* SSH Keygen
```bash
$ ssh-keygen -t rsa
```

* Copy Key
```bash
$ cp ~/.ssh/id_rsa.pub ~/git-server/keys
$ cp ~/.ssh/id_rsa ~/git-server/keys
```

* Test SSH
```bash
$ ssh git@10.100.100.244 -p 222
```

* Exec Container
```bash
$ docker exec -it [container_id] sh
```

* Create Repository
```bash
$ mkdir repos/nida
```

* Git Init
```bash
$ git init --shared=true
```

* Git Add
```bash
$ git add .
```

* Git Config
```bash
$ git config --global user.email "natthasath.sak@nida.ac.th"
$ git config --global user.name "natthasath.sak"
```

* Git Commit
```bash
$ git commit -m "first commit"
```

* Git Clone Bare
```bash
$ git clone --bare nida nida.git
```

* Move Clone Bare
```bash
$ mv nida.git ~/git-server/repos
```

* Git Clone
```bash
$ git clone ssh://git@10.100.100.244:222/git-server/repos/nida.git
```

* Alpine APK Update
```bash
# apk update && apk upgrade
```

* Alpine Upgrade Latest Version
```bash
# cat /etc/alpine-release
# vi /etc/apk/repositories
edit_text> http://dl-cdn.alpinelinux.org/alpine/v3.7/main
# apk update
# apk upgrade --available
# apk upgrade --purge
# sync
# reboot
```

* Install Apache & PHP7
```bash
# apk search apache php7
# apk add apache2 php7 php7-fpm php7-opcache
# apk add php7-gd php7-mysqli php7-zlib php7-curl
https://www.cyberciti.biz/faq/how-to-install-php-7-fpm-on-alpine-linux/
```

* Install OpenRC
```bash
# apk add openrc --no-cache
https://github.com/gliderlabs/docker-alpine/issues/183
```

* Service Start on System Reboot
```bash
# rc-update add apache2 default
# rc-update add php-fpm7 default
# rc-service php-fpm7 restart
# rc-service apache2 restart
```

* Fix Apache2
```bash
# mkdir -p /run/apache2
# httpd -k start
https://forum.alpinelinux.org/forum/general-discussion/apache2-fail-start
```

* Fix PHP7
```bash
# mkdir -p /run/php7
# php7 -k start
https://forum.alpinelinux.org/forum/general-discussion/apache2-fail-start
```

* Netstat
```bash
# apk add ospd-netstat
# netstat -r
# netstat -a
# netstat -ano
```

## Credit
https://hub.docker.com/r/jkarlos/git-server-docker/