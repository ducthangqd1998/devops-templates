# RHELL

**Set up the repository**

Install the `yum-utils` package (which provides the `yum-config-manager` utility) and set up the **stable** repository.

```shell
 sudo yum install -y yum-utils
 sudo yum-config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
```

**Install Docker Engine**

1. Install the latest version of Docker Engine and containerd, or go to the next step to install a specific version:
    ```shell
    sudo yum install docker-ce docker-ce-cli containerd.io
    ```
