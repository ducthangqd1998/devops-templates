### Centos 7
Create or edit file using vim/vi/joe text editor:
```shell
sudo vi /etc/yum.repos.d/nginx.repo
```
```bash
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/mainline/rhel/7/$basearch/
gpgcheck=0
enabled=1
```

Install nginx server
```shell
sudo yum install nginx
```
Start/stop/restart nginx server
```shell
sudo systemctl enable nginx
```

Start nginx command

```shell
sudo systemctl start nginx
```

### RedHat

Create or edit file using vim/vi/joe text editor:
```shell
sudo vi /etc/yum.repos.d/nginx.repo
```
```shell
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/mainline/rhel/7/$basearch/
gpgcheck=0
enabled=1
```
Install nginx server
```shell
sudo yum install nginx
```
Start/stop/restart nginx server
```shell
sudo systemctl enable nginx
```

Start nginx command
```shell
sudo systemctl start nginx
```

### Firewall Configure
Open port 80 and 443 using firewall-cmd

```shell
sudo firewall-cmd --permanent --zone=public --add-service=http
sudo firewall-cmd --permanent --zone=public --add-service=https
sudo firewall-cmd --reload
```

Verify that port 80 or 443 opened using ss command:
```shell
sudo ss -tulpn
```

### Install Certbot

Let’s install the EPEL package:
```shell
yum install epel-release
```
If the output is `No package epel-release available.`, you can install `epel` via ...
```shell
yum install http://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm

```
Then update the packages in the system to add the new package lists to the package manager:
```shell
yum update
```
Now, we will install certbot by running this command:
```shell
yum install certbot-nginx
```

Register domain with nginx server.
```shell
sudo certbot --nginx -d [domain-name]
```