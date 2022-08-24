# flutter chinization

> flutter使用国内源安装，以gitee的flutter仓库源为例

## Flutter源拉取

```shell
git clone https://gitee.com/mirrors/Flutter.git
```

## flutter&dart环境变量配置

> 注意修改FLUTTER_HOME为自己本地拉取代码的FLUTTER目录

```shell
export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
export FLUTTER_HOME=~/Flutter
export DART_HOME=$FLUTTER_HOME/cache/bin/cache/dart-sdk
export PATH=$FLUTTER_HOME/bin:$DART_HOME/bin:$PATH
```

## flutter&dart版本查看

```shell
dart --version  
flutter --version
````

## 初始化flutter及检查

```shell
flutter doctor
```

## flutter升级

```shell
flutter upgrade
```
