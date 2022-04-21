
### CentOS/RHEL/Fedora/Amazon Linux 2

**Step #1: Add the Official GitLab Repository**
First add the official GitLab Repository using below command, to check latest Gitlab Repository visit the official GitLab Runner page

```shell
curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.rpm.sh" | sudo bash
```
**Step #2: Install GitLab Runner on CentOS/RHEL/Fedora**
Run below command to install latest GitLab Runner on CentOS/RHEL/Fedora

```shell
sudo yum install gitlab-runner
```
Command to check GitLab Runner version

```shell
sudo gitlab-runner -version
```

To check status if GitLab Runner service is running or not

```shell
sudo gitlab-runner status
```

Commands to Start, Stop and Restart GitLab Runner
```shell
sudo gitlab-runner start
sudo gitlab-runner stop
sudo gitlab-runner restart
```
**Step #3: Grant sudo Permission to GitLab Runner User**
After install GitLab Runner you will see gitlab-runner user in /home directory

```shell
sudo visudo
```
Add the gitlab-runner user in sudoers group and set **NOPASSWD** as shown below


```
## Allow gitlab-runner access without a password
gitlab-runner ALL=(ALL:ALL) ALL
gitlab-runner ALL=(ALL) NOPASSWD: ALL
```