# ubuntu chinization

> ubuntu使用国内apt源，以ubuntu较为常用的20.04版本为例，其他版本参见...

## 替换源为阿里云

备份原```/etc/apt/sources.list```

```shell
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
```

编辑```/etc/apt/sources.list```替换其中```http://archive.ubuntu.com/```为```https://mirrors.aliyun.com/```，例如ubuntu22.04最后的配置文件为

```text
deb https://mirrors.aliyun.com/ubuntu/ focal main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ focal main restricted universe multiverse

deb https://mirrors.aliyun.com/ubuntu/ focal-security main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ focal-security main restricted universe multiverse

deb https://mirrors.aliyun.com/ubuntu/ focal-updates main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ focal-updates main restricted universe multiverse

# deb https://mirrors.aliyun.com/ubuntu/ focal-proposed main restricted universe multiverse
# deb-src https://mirrors.aliyun.com/ubuntu/ focal-proposed main restricted universe multiverse

deb https://mirrors.aliyun.com/ubuntu/ focal-backports main restricted universe multiverse
deb-src https://mirrors.aliyun.com/ubuntu/ focal-backports main restricted universe multiverse
```

更新本地的apt源

```shell
sudo apt update
```

## 还原为官方源

```shell
sudo rm -f /etc/apt/sources.list
sudo mv /etc/apt/sources.list.bak /etc/apt/sources.list
sudo apt update
```
