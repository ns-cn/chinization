# npm chinization

> npm使用国内源，以使用阿里云的npm源为例
> 
> 注：[```http://npm.taobao.org```和```http://registry.npm.taobao.org```已在 2022.06.30 号正式下线和停止 DNS 解析](https://developer.aliyun.com/mirror/NPM)

## 替换为阿里npm源

```shell
npm set registry http://registry.npmmirror.com
```

## cnpm：阿里云提供的默认命令行工具的替代品

#### 安装cnpm

```shell
npm install -g cnpm --registry=https://registry.npmmirror.com
```

#### 或者你直接通过添加 npm 参数 alias 一个新命令:

```shell
alias cnpm="npm --registry=https://registry.npmmirror.com \
--cache=$HOME/.npm/.cache/cnpm \
--disturl=https://npmmirror.com/mirrors/node \
--userconfig=$HOME/.cnpmrc"

# Or alias it in .bashrc or .zshrc
$ echo '\n#alias for cnpm\nalias cnpm="npm --registry=https://registry.npmmirror.com \
  --cache=$HOME/.npm/.cache/cnpm \
  --disturl=https://npmmirror.com/mirrors/node \
  --userconfig=$HOME/.cnpmrc"' >> ~/.zshrc && source ~/.zshrc
```

#### 使用cnpm安装模块

```shell
cnpm install [name]
```

#### 同步模块

> 直接通过 sync 命令马上同步一个模块, 只有 cnpm 命令行才有此功能:

```shell
cnpm sync express
```
