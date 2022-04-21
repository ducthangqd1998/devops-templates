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