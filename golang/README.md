# golang chinization

> golang安装及代理源的替换，以华为goproxy为例

安装步骤参见官方说明：[https://golang.google.cn/doc/install](https://golang.google.cn/doc/install)

## 设置goproxy代理

> 请注意确保golang版本为1.11以上


方式1：临时设置

```shell
export GO111MODULE=on
export GOPROXY=https://repo.huaweicloud.com/repository/goproxy/
export GONOSUMDB=*
```

方式2：修改goproxy并保存

```shell
go env -w GO111MODULE=on
go env -w GOPROXY=https://repo.huaweicloud.com/repository/goproxy/
go env -w GONOSUMDB=*
```

其他镜像

- 阿里云：[https://mirrors.aliyun.com/goproxy/,direct](https://mirrors.aliyun.com/goproxy/,direct)
- 七牛云：[https://goproxy.cn,direct](https://goproxy.cn,direct)
- goproxy.cn：[https://goproxy.cn,direct](https://goproxy.cn,direct)

## 重置为官方源

```shell
go env -w GOPROXY=https://goproxy.io,direct
go env -w GO111MODULE=on
```

或者使用

```shell
go env -u GOPROXY
```
