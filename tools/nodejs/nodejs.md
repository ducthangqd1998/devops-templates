# NodeJS

### Centos

**Step 1 – Add Node.js Yum Repository**
First of all, You need to enable node.js yum repository in your system provided by the Node.js official website. You also need development tools to build native add-ons to be installed on your system.

For Latest Release:-

```shell
sudo yum install -y gcc-c++ make 
curl -sL https://rpm.nodesource.com/setup_16.x | sudo -E bash - 
```
For Stable Release:-

```shell
sudo yum install -y gcc-c++ make 
curl -sL https://rpm.nodesource.com/setup_14.x | sudo -E bash -
```

**Step 2 – Install Node.js on CentOS**

After adding a yum repository in your system lets install Node.js package. NPM will also be installed with node.js. This command will also install many other dependent packages on your system.

```shell
sudo yum install nodejs 
```
**Step 4 Install pm2**

```shell
sudo npm install pm2@latest -g
```

### Ubuntu

To install a different version of Node.js, you can use a PPA (personal package archive) maintained by NodeSource. These PPAs have more versions of Node.js available than the official Ubuntu repositories. Node.js v12, v14, and v16 are available as of the time of writing.

First, we will install the PPA in order to get access to its packages. From your home directory, use curl to retrieve the installation script for your preferred version, making sure to replace 16.x with your preferred version string (if different).
```shell
cd ~
curl -sL https://deb.nodesource.com/setup_14.x -o /tmp/nodesource_setup.sh
```
Refer to the NodeSource documentation for more information on the available versions.

Inspect the contents of the downloaded script with nano (or your preferred text editor):
```shell
nano /tmp/nodesource_setup.sh
```
When you are satisfied that the script is safe to run, exit your editor, then run the script with sudo:
```shell
sudo bash /tmp/nodesource_setup.sh
```
The PPA will be added to your configuration and your local package cache will be updated automatically. You can now install the Node.js package in the same way you did in the previous section:
```shell
sudo apt install nodejs
```
Verify that you’ve installed the new version by running node with the -v version flag:
```shell
node -v
```
```shell
Output
v16.6.1
```