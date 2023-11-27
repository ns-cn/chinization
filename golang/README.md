# golang chinization

> golang安装及代理源的替换，以华为goproxy为例

安装步骤参见官方说明：[https://golang.google.cn/doc/install](https://golang.google.cn/doc/install)

## 设置goproxy代理

> 请注意确保golang版本为1.11以上

启用go mod： `export GO111MODULE=on`；方式1：临时设置；方式2：修改goproxy并保存

| 源   | 方式一                                                                      | 方式2                                                                         |
|-----|--------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| 官方源 | `export GOPROXY=https://goproxy.io,direct`                               | `go env -w GOPROXY=https://goproxy.io,direct`                               |
| 华为云 | `export GOPROXY=https://repo.huaweicloud.com/repository/goproxy/,direct` | `go env -w GOPROXY=https://repo.huaweicloud.com/repository/goproxy/,direct` |
| 阿里云 | `export GOPROXY=https://mirrors.aliyun.com/goproxy/,direct`              | `go env -w GOPROXY=https://mirrors.aliyun.com/goproxy/,direct`              |
| 七牛云 | `export GOPROXY=https://goproxy.cn,direct`                               | `go env -w GOPROXY=https://goproxy.cn,direct`                               |

## 重置为官方源

切换为官方源；或者使用如下命令

```shell
go env -u GOPROXY
```
