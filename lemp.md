# Configure LEMP

LEMP es un grupo de software que se puede utilizar para servir páginas web dinámicas y aplicaciones web. Este es un acrónimo 
que describe un sistema operativo Linux, con un servidor web Nginx.
Los datos del backend se almacenan en la base de datos MySQL y el procesamiento dinámico es manejado por PHP.

## Nginx
```sh
sudo apt-get update
sudo apt-get install nginx
```
Permitir tráfico en el puerto 80.

Podemos habilitarlo escribiendo:

```sh
sudo ufw allow 'Nginx HTTP' 
```

Puede verificar el cambio escribiendo:

```sh
sudo ufw status 
```
## MariaDB

```sh
apt-get update
apt-get upgrade  

sudo apt-get install software-properties-common
sudo apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
sudo add-apt-repository 'deb [arch=amd64,i386,ppc64el] http://ftp.utexas.edu/mariadb/repo/10.1/ubuntu xenial main

apt-get install mariadb-server

```
Para comprobar si se instalo correctamente

```sh
systemctl start mariadb
systemctl status mariadb

```
Para iniciar sesión `mysql -u root -p`

### Php 7

Para instalar php7.1 en linux

```sh
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update 
sudo apt-get install php7.1 

```
### Composer

```sh
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```
Despues `mv composer.phar /usr/local/bin/composer`
