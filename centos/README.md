# centos chinization

> centos替换使用国内镜像源，以centos8替换使用阿里云源为例，其他请参见[README](../README.md)中提供的centos镜像源的说明

## 配置使用阿里云源

备份

```shell
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```

下载新的 CentOS-Base.repo 到 /etc/yum.repos.d/
> centos8（centos8官方源已下线，建议切换centos-vault源）
```shell
wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-vault-8.5.2111.repo
```
或者
```shell
curl -o /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-vault-8.5.2111.repo
```

刷新本地缓存
```shell
yum makecache
```

## 还原使用官方源

> 使用备份文件还原官方源


```shell
rm /etc/yum.repos.d/CentOS-Base.repo.backup
mv /etc/yum.repos.d/CentOS-Base.repo.backup /etc/yum.repos.d/CentOS-Base.repo
yum makecache
```
