# PHP 8

### Install 
#### Amazon Linux 2
Update the system before starting the installation of PHP 8 on Amazon Linux 2 system.

```shell
sudo yum -y update
```
Add EPEL and Remi Repositories

```shell
sudo yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
sudo yum -y install https://rpms.remirepo.net/enterprise/remi-release-7.rpm
```
Install PHP 8.0 on Amazon Linux 2. Install the yum-utils package which provides yum-config-manager command line tool.

```shell
sudo yum -y install yum-utils
```
Let’s confirm that PHP 8.0 topic is available in our Amazon Linux 2 machine:
```shell
sudo  amazon-linux-extras | grep php
```
We can confirm php8.0 topic is available. Let’s enable it.
```shell
sudo yum-config-manager --disable 'remi-php*'
sudo amazon-linux-extras enable php8.0 
```
After repo is enabled, install PHP 8.0 on Amazon Linux 2 with standard PHP extensions.
```shell
sudo yum clean metadata
sudo yum install php-{pear,cgi,pdo,common,curl,mbstring,gd,mysqlnd,gettext,bcmath,json,xml,fpm,intl,zip}
```
Check PHP version
```shell
php --version
```

Install Composer
```shell
cd ~
sudo curl -sS https://getcomposer.org/installer | sudo php
sudo mv composer.phar /usr/local/bin/composer
sudo ln -s /usr/local/bin/composer /usr/bin/composer
sudo composer install
```
