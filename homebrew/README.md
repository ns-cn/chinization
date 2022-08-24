# homebrew chinization

> homebrew带国内源的安装、替换、还原，以中科大镜像源为例，其他请参见[README](../README.md)中提供homebrew镜像源的说明

## 初次安装使用国内源的homebrew

首先在命令行运行如下几条命令设置环境变量：

```shell
export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.ustc.edu.cn/brew.git"
export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.ustc.edu.cn/homebrew-core.git"
export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.ustc.edu.cn/homebrew-bottles"
```

之后在命令行运行 Homebrew 安装脚本：

```shell
/bin/bash -c "$(curl -fsSL https://github.com/Homebrew/install/raw/HEAD/install.sh)"
```

> 若github无法访问，可使用JSDeliverCDN替换
> ```shell
> /bin/bash -c "$(curl -fsSL https://cdn.jsdelivr.net/gh/Homebrew/install@HEAD/install.sh)"
> ```

## 替换已安装homebrew使用国内源
替换 USTC 镜像：

```shell
export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.ustc.edu.cn/brew.git"
brew update
```

> 若用户设置了环境变量```HOMEBREW_BREW_GIT_REMOTE```，则每次运行```brew update```时将会自动设置远程。 推荐用户将环境变量```HOMEBREW_BREW_GIT_REMOTE```加入shell的profile设置中。
> 对于 bash 用户
> ```
> echo 'export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.ustc.edu.cn/brew.git"' >> ~/.bash_profile
> ```
> 对于 zsh 用户
> ```
> echo 'export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.ustc.edu.cn/brew.git"' >> ~/.zshrc
> ```

## 重置为官方源

```shell
unset HOMEBREW_BREW_GIT_REMOTE
git -C "$(brew --repo)" remote set-url origin https://github.com/Homebrew/brew
```

> 重置回默认远程后，用户应该删除 shell的profile设置中的环境变量```HOMEBREW_BREW_GIT_REMOTE``` 以免运行 ```brew update``` 时远程再次被更换。
> 
> 若之前使用的 ```git config url.<URL>.insteadOf URL``` 的方式设置的镜像，请手动删除config文件（一般为 ```~/.gitconfig``` 或仓库目录下的```.git/config```）中的对应字段。
