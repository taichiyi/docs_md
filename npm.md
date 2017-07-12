![logo](http://oop4q34sz.bkt.clouddn.com/npm.png)

# npm (node package manager)

[init](#init) [install](#install) [uninstall](#uninstall) [update](#update) [publish](#publish) [config](#config) 


## init

在当前文件夹创建一个package.json文件

### 语法
```Bash
npm init [-f|--force|-y|--yes]
```

### 实例

当你输入`$ npm init`回车后, 它会提示你输入一些配置信息, 如果某个配置你想跳过的话, 回车就行了.
```
$ npm init
```

如果都使用默认配置的话, 添加`-y`或`--yes`
```
$ npm init -y
# 等同于
$ npm init --yes
```


## install

添加一个模块

每个模块可以“全局安装”，也可以“本地安装”。“全局安装”指的是将一个模块安装到系统目录中，各个项目都可以调用。一般来说，全局安装只适用于工具模块，比如eslint和gulp。“本地安装”指的是将一个模块下载到当前项目的node_modules子目录，然后只有在项目目录之中，才能调用这个模块。

安装之前，npm install会先检查，node_modules目录之中是否已经存在指定模块。如果存在，就不再重新安装了，即使远程仓库已经有了一个新版本，也是如此。

### 语法
```Bash
npm install (with no args, in package dir)
npm install [<@scope>/]<name>
npm install [<@scope>/]<name>@<tag>
npm install [<@scope>/]<name>@<version>
npm install [<@scope>/]<name>@<version range>
npm install <tarball file>
npm install <tarball url>
npm install <folder>

alias: npm i
common options: [-S|--save|-D|--save-dev|-O|--save-optional] [-E|--save-exact] [-B|--save-bundle] [--dry-run]
```

### 实例

本地安装`gulp`模块
```
$ npm install gulp
```

全局安装`gulp`模块
```
$ npm install -g gulp
```

本地安装`gulp`模块, 并把依赖关系写入package.json里
```
$ npm install -save gulp
```


## uninstall

卸载一个模块

### 语法
```Bash
npm uninstall [<@scope>/]<pkg>[@<version>]... [-S|--save|-D|--save-dev|-O|--save-optional]

aliases: remove, rm, r, un, unlink
```

### 实例

卸载本地安装的模块
```
$ npm uninstall gulp
```

卸载全局安装的模块
```
$ npm uninstall -g gulp
```

卸载`gulp`模块, 并修改package.json里的依赖关系
```
$ npm uninstall -save gulp
```


## update

更新一个模块

### 语法
```Bash
npm update [-g] [<pkg>...]

aliases: up, upgrade
```

### 实例

更新本地安装的`gulp`模块
```
# 要在相应的package.json所在目录下运行
$ npm update gulp
```

更新全局安装的`gulp`模块
```
$ npm update -g gulp
```

## publish

发布一个模块

### 语法

```Bash
npm publish [<tarball>|<folder>] [--tag <tag>] [--access <public|restricted>]

Publishes '.' if no argument supplied
Sets tag 'latest' if no --tag specified
```

### 实例

运行前，请确认当前目录的package.json

```
$ npm publish
```

## config

查看或修改配置信息

### 语法

```Bash
npm config set <key> <value> [-g|--global]
npm config get <key>
npm config delete <key>
npm config list
npm config edit
npm get <key>
npm set <key> <value> [-g|--global]

aliases: c
```

### 实例

查看name属性

```
$ npm config get name
```

查看registry属性

```
$ npm config get registry
```

设置registry属性

```
$ npm config set registry https://registry.npm.taobao.org
```

设置，使用npm init时，生成的package.json文件的name字段的默认值为'taichiyi'。

```
$ npm config set init.author.name taichiyi
```

查看配置列表

```
$ npm config ls
```

## 参考链接

[https://docs.npmjs.com/](https://docs.npmjs.com/)  
[http://javascript.ruanyifeng.com/nodejs/npm.html](http://javascript.ruanyifeng.com/nodejs/npm.html)  
