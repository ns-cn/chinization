# docker chinization

> docker替换国内源使用，本例以中科大源为例，使用阿里云镜像可参考[阿里云docker操作文档](https://cr.console.aliyun.com/cn-hangzhou/instances/mirrors)申请并修改docker配置

## macos替换国内源

针对安装了Docker for Mac的用户，在Perfernces->Docker Engine，在右侧输入栏编辑json文件，将镜像源配置写入json中，点击Apply后等待Docker重启并应用配置

```json
{
  "registry-mirrors": ["https://docker.mirrors.ustc.edu.cn"]
}
```

## ubuntu/centos替换国内源

将如下镜像源配置写入```/etc/docker/daemon.json```

```json
{
  "registry-mirrors": ["https://docker.mirrors.ustc.edu.cn"]
}
```

重启docker

```shell
sudo systemctl daemon-reload
sudo systemctl restart docker
```

## windows替换国内源

针对安装了Docker for Windows的用户，在Settings-> Docker Daemon，在右侧输入栏编辑json文件，将镜像源配置写入json中，点击Apply后等待Docker重启并应用配置

```json
{
  "registry-mirrors": ["https://docker.mirrors.ustc.edu.cn"]
}
```


## 重置为官方源

按对应步骤删除json中镜像源的配置即可
