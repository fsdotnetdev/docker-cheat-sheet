# Snipe-IT Docker

## Package
* composer
* unzip

## Install Snipe-IT
* Update & Upgrade Ubuntu
```bash
# apt-get update && apt-get upgrade
```

* Install MySQL
```bash
# apt-get install mysql-server
# mysql_secure_installation
```

* Pull
```bash
$ docker pull fsdotnet/snipe-it
```

* Database
```bash
docker run --name snipe-mysql --env-file=snipe.env -d -p $(docker-machine ip b2d)::3306 mysql:5.6
```

* Run
```bash
$ docker run -d -p 80:80 -p 443:443 --name="snipeit" --link snipe-mysql:mysql --env-file=snipe.env snipe/snipe-it
```

## Credit
https://hub.docker.com/r/jkarlos/git-server-docker/


apt-get install git -y
git clone https://github.com/snipe/snipe-it snipe-it
mysql -u root -p
cd snipe-it/
curl -sS https://getcomposer.org/installer | php
php composer.phar install --no-dev --prefer-source
php artisan key:generate
nano .env
cp .env.example .env
php artisan key:generate
./install.sh

* MySQL
apt-get -y install mysql-server mysql-client
apt-get -y install mariadb-server mariadb-client
mysql_secure_installation
mysql -u root -p

* Apache
```bash
apt-get -y install apache2
apt-get -y install php7.0 libapache2-mod-php7.0
service apache2 start
vi /var/www/html/info.php
```

apt-get -y install phpmyadmin
cd /var/www/html/
ls -lrt
ln -s /usr/share/phpmyadmin/ /var/www/html/
ls -lrt
systemctl restart apache2
mysql -u root -p
nano /etc/hostname
nano /etc/hosts

cd /var/www/snipe-it/
nano .env
./install.sh
mysql -u root -p
nano .env
cd /etc/apache2/sites-available/
ls -lrt
a2dissite 000-default.conf
a2ensite snipeit.conf
a2enmod rewrite
rite
Module rewrite already enabled
nano snipeit.conf
systemctl restart apache2
ping 10.100.100.240
cd /var/www/
ls -lrt
cd snipeit
ls -lrt
cd ../
cd snipe-it
ls -lrt


https://snipe-it.readme.io/docs/creating-a-database-and-user
https://www.digitalocean.com/community/tutorials/how-to-install-snipe-it-on-ubuntu-16-04
https://hub.docker.com/r/snipe/snipe-it/~/dockerfile/