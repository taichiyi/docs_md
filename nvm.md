
# nvm(Node Version Manager)

[install](#install) [use](#use) [ls](#ls) [ls-remote](#ls-remote) [current](#current) [reinstall-packages](#reinstall-packages) [uninstall](#uninstall) [update](#update) 


## install

安装指定版本，可模糊安装。

### 语法
```Bash
nvm install <version>
```

### 实例

安装`7.5.0`版本
```
$ nvm install v7.5.0
```

安装最新版
```
$ nvm install stable
```

模糊安装4.4
```
$ nvm install 4.4
```

## use

切换指定的版本

### 语法
```Bash
nvm use <version>
```

### 实例

```
$ nvm use 8.0.0
```

## ls

列出所有已安装版本

### 语法
```Bash
nvm ls
```

### 实例

```
$ nvm ls
```

## ls-remote

列出所有远程服务器版本（官方node version list）

### 语法
```Bash
nvm ls-remote
```

### 实例

```
$ nvm ls-remote
```

## current

显示当前使用的版本

### 语法
```Bash
nvm current
```

### 实例

```
$ nvm current
```

## reinstall-packages

在当前node环境下，重新全局安装指定版本

### 语法
```Bash
nvm reinstall-packages <version>
```

### 实例

```
$ nvm reinstall-packages 7.5.0
```

## uninstall

卸载一个版本

### 语法
```Bash
nvm uninstall <version>
```

### 实例

卸载7.5.0版本
```
$ nvm uninstall 7.5.0
```


## update

更新一个模块

### 语法
```Bash
nvm update [-g] [<pkg>...]

aliases: up, upgrade
```

### 实例

更新本地安装的`gulp`模块
```
# 要在相应的package.json所在目录下运行
$ nvm update gulp
```

更新全局安装的`gulp`模块
```
$ nvm update -g gulp
```

## publish

发布一个模块

### 语法

```Bash
nvm publish [<tarball>|<folder>] [--tag <tag>] [--access <public|restricted>]

Publishes '.' if no argument supplied
Sets tag 'latest' if no --tag specified
```

### 实例

更新本地安装的`gulp`模块

```
# 要在相应的package.json所在目录下运行
$ nvm update gulp
```

更新全局安装的`gulp`模块

```
$ nvm update -g gulp
```

## 参考链接

[https://docs.nvmjs.com/](https://docs.nvmjs.com/)  
