### Install

#### Amazon Linux 2

**Step 1: Add MySQL Yum Repository to Amazon Linux 2**

```shell
sudo yum install https://dev.mysql.com/get/mysql80-community-release-el7-5.noarch.rpm
```

**Step 2: Install MySQL 8 on Amazon Linux 2**
```shell
sudo amazon-linux-extras install epel -y
sudo yum -y install mysql-community-server
```

**Step 3: Start and Configure MySQL 8 on Amazon Linux 2**
```
sudo systemctl enable --now mysqld
```

A superuser account ‘root’@’localhost is created with initial password set and stored in the error log file. To reveal it, use the following command:

```shell
sudo grep 'temporary password' /var/log/mysqld.log
```
Use this initial password to harden the server.


```shell
sudo mysql_secure_installation -p
```

### Change root password
#### Centos 7

MySQL >= `8.0`
```shell
# stop mysql
sudo systemctl stop mysqld

# set the mysql environment option
systemctl set-environment MYSQLD_OPTS="--skip-grant-tables"

# start mysql using the options you just set
sudo systemctl start mysqld

# login as root user
mysql -u root

# update password for root user
mysql > UPDATE mysql.user SET authentication_string=null WHERE User='root';
mysql > FLUSH PRIVILEGES;
mysql > exit

# login again
mysql > ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'yourpasswd';

# disable --skip-grant-tables to mysql open port on your localhost
sudo systemctl set-environment MYSQLD_OPTS=""

# stop mysql
sudo systemctl stop mysqld

# start mysql service
sudo systemctl start mysqld

# login root user with your password has changed
mysql -u root -p
> Enter password: ....
```