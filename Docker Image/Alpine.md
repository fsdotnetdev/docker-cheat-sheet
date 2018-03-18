# Alpine

* Pull
```bash
$ docker pull alpine
```

* Run
```bash
$ docker run -it -d -p 2222:22 -p 80:80 -p 443:443 alpine /bin/sh
```

* Exec Container
```bash
$ docker exec -it [container_id] sh
```

* Alpine APK Update
```bash
# apk update && apk upgrade
```

* Install Apache & PHP
```bash
# apk add apache2 php5-apache2
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

* 

## Credit
https://wiki.alpinelinux.org/wiki/Setting_Up_Apache_with_PHP