### Install


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