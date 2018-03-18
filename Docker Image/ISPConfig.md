# ISPConfig
Documentation
```bash

```

## Dockerfile
```bash
# Download Base Image Ubuntu Latest Version 16.04
FROM ubuntu:latest

# Author Dockerfile
MAINTAINER fsdotnet <fsdotnetdev@gmail.com>

# 1. Update & Upgrade Ubuntu
RUN apt-get update && apt-get -y upgrade

# 2. Install Tool Package
RUN apt-get -y install openssh-server vim

# 3. Change the Default Shell
RUN echo "dash  dash/sh boolean no" | debconf-set-selections
RUN dpkg-reconfigure dash

# 5. Synchronize the System Clock
RUN apt-get -y install ntp ntpdate

# 6. Install Postfix, Dovecot, MariaDB, rkhunter and binutils
RUN apt-get -y install postfix postfix-mysql postfix-doc mariadb-client mariadb-server openssl getmail4 rkhunter binutils dovecot-imapd dovecot-pop3d dovecot-mysql dovecot-sieve dovecot-lmtpd

RUN service postfix restart
RUN service mysql restart








# Default Command
CMD ["/bin/bash", "/start.sh"]
```

## Docker ISPConfig
```bash
$ docker run --name ispconfig  -e MAILMAN_EMAIL_HOST=test.com -e MAILMAN_EMAIL=test@test.com -e MAILMAN_PASS=pass -d -p 20:20 -p 21:21 -p 30000:30000 -p 30001:30001 -p 30002:30002 -p 30003:30003 -p 30004:30004 -p 30005:30005 -p 30006:30006 -p 30007:30007 -p 30008:30008 -p 30009:30009 -p 80:80 -p 443:443 -p 8080:8080 -p 53:53 -p 2222:22 jerob/docker-ispconfig /start.sh

docker run --name ispconfig  -p 20:20 -p 21:21 -p 30000:30000 -p 30001:30001 -p 30002:30002 -p 30003:30003 -p 30004:30004 -p 30005:30005 -p 30006:30006 -p 30007:30007 -p 30008:30008 -p 30009:30009 -p 80:80 -p 443:443 -p 8080:8080 -p 53:53 -p 2222:22 jerob/docker-ispconfig /start.sh
```

## Credit
