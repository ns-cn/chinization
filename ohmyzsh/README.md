# oh-my-zsh chinization

> oh my zsh使用gitee镜像安装

## 使用gitee镜像全新安装

从gitee下载install.sh

```shell
wget https://gitee.com/mirrors/oh-my-zsh/raw/master/tools/install.sh
```

替换install.sh中仓库地址为gitee地址

```shell
sed -i 's/REPO=${REPO:-ohmyzsh\/ohmyzsh}/REPO=${REPO:-mirrors\/oh-my-zsh}/' install.sh
sed -i 's/REMOTE=${REMOTE:-https:\/\/github.com\/${REPO}.git}/REMOTE=${REMOTE:-https:\/\/gitee.com\/${REPO}.git}/' install.sh
```

添加权限并执行install.sh

```shell
chmod +x install.sh
./install.sh
```

## 已安装替换为gitee仓库

```shell
cd ~/.oh-my-zsh
git remote set-url origin https://gitee.com/mirrors/oh-my-zsh.git
 
# 查看
git remote -v
```

## 配置oh-my-zsh

禁用自动更新

```shell
sed -i 's/# DISABLE_AUTO_TITLE="true"/DISABLE_AUTO_TITLE="true"/' ~/.zshrc 
```

手动执行更新

```shell
upgrade_oh_my_zsh
 
# 或者
./.oh-my-zsh/tools/upgrade.sh 
```
