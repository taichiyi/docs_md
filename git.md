![logo](http://oop4q34sz.bkt.clouddn.com/logo@2x.png)

# git

[clone](#clone) [remote](#remote) [fetch](#fetch) [pull](#pull) [push](#push) [config](#config)

![pic](http://oop4q34sz.bkt.clouddn.com/bg2014061202.jpg)


## clone

克隆一个版本库到新目录

### 语法
```Bash
git clone [--template=<template_directory>]
          [-l] [-s] [--no-hardlinks] [-q] [-n] [--bare] [--mirror]
          [-o <主机名>] [-b <主机名>] [-u <upload-pack>] [--reference <repository>]
          [--dissociate] [--separate-git-dir <git dir>]
          [--depth <depth>] [--[no-]single-branch]
          [--recursive | --recurse-submodules] [--[no-]shallow-submodules]
          [--jobs <n>] [--] <repository> [<directory>]
```

### 实例

<repository\>的种类
```
$ git clone http[s]://example.com/path/to/repo.git/
$ git clone ssh://example.com/path/to/repo.git/
$ git clone git://example.com/path/to/repo.git/
$ git clone /opt/git/project.git 
$ git clone file:///opt/git/project.git
$ git clone ftp[s]://example.com/path/to/repo.git/
$ git clone rsync://example.com/path/to/repo.git/
```

克隆版本库的时候，所使用的远程主机自动被Git命名为origin。如果想用其他的主机名，需要用git clone命令的-o选项指定。
```
$ git clone -o jQuery https://github.com/jquery/jquery.git
```


## remote

管理查询版本库

### 语法
```Bash
git remote [-v | --verbose]
git remote add [-t <branch>] [-m <master>] [-f] [--[no-]tags] [--mirror=<fetch|push>] <主机名> <网址>
git remote rename <old> <new>
git remote remove <主机名>
git remote set-head <主机名> (-a | --auto | -d | --delete | <branch>)
git remote set-branches [--add] <主机名> <branch>…​
git remote get-url [--push] [--all] <主机名>
git remote set-url [--push] <主机名> <newurl> [<oldurl>]
git remote set-url --add [--push] <主机名> <newurl>
git remote set-url --delete [--push] <主机名> <网址>
git remote [-v | --verbose] show [-n] <主机名>…​
git remote prune [-n | --dry-run] <主机名>…​
git remote [-v | --verbose] update [-p | --prune] [(<group> | <remote>)…​]
```

### 实例

列出所有远程主机
```
$ git remote
```

列出所有远程主机的网址
```
$ git remote -v
```

查看指定远程主机的详细信息
```
$ git remote show <主机名>
$ git remote show origin
```

添加远程主机
```
$ git remote add <主机名> <网址>
$ git remote add jQuery https://github.com/jquery/jquery.git
```

删除远程主机
```
$ git remote rm <主机名>
$ git remote rm jQuery
```

修改远程主机名
```
$ git remote rename <原主机名> <新主机名>
$ git remote rename jQuery jQuery1
```


## fetch

取回本地

一旦远程主机的版本库有了更新（Git术语叫做commit），需要将这些更新取回本地，这时就要用到`git fetch`命令。

### 语法
```Bash
git fetch [<options>] [<repository> [<refspec>…​]]
git fetch [<options>] <group>
git fetch --multiple [<options>] [(<repository> | <group>)…​]
git fetch --all [<options>]
```

### 实例

将某个远程主机的更新，全部取回本地。
```
$ git fetch <远程主机名>
$ git fetch origin
```

取回远程主机某个分支的更新
```
$ git fetch <远程主机名> <分支名>
$ git fetch origin master
```


## pull

取回本地+合并

`git pull`命令的作用是，取回远程主机某个分支的更新，再与本地的指定分支合并。它的完整格式稍稍有点复杂。

### 语法
```Bash
git pull [options] [<repository> [<refspec>…​]]
```

### 实例

取回`origin`主机的`next`分支，与本地的`master`分支合并，需要写成下面这样。
```
$ git pull origin next:master
```

如果远程分支是与当前分支合并，则冒号后面的部分可以省略。
取回`origin/next`分支，再与当前分支合并。实质上，等同于先做`git fetch`，再做`git merge`。
```
$ git pull origin next
```


## push

推出本地

`git push`命令用于将本地分支的更新，推送到远程主机。它的格式与`git pull`命令相仿。

### 语法
```Bash
git push [--all | --mirror | --tags] [--follow-tags] [--atomic] [-n | --dry-run] [--receive-pack=<git-receive-pack>]
         [--repo=<repository>] [-f | --force] [-d | --delete] [--prune] [-v | --verbose]
         [-u | --set-upstream] [--push-option=<string>]
         [--[no-]signed|--sign=(true|false|if-asked)]
         [--force-with-lease[=<refname>[:<expect>]]]
         [--no-verify] [<repository> [<refspec>…​]]
```

### 实例

```
$ git push <远程主机名> <本地分支名>:<远程分支名>
```
本地的`master`分支推送到`origin`主机的`master`分支。如果后者不存在，则会被新建。
```
$ git push origin master
```

删除`origin`主机的`master`分支。
```
$ git push origin :master
# 等同于
$ git push origin --delete master
```

如果当前分支与多个主机存在追踪关系，则可以使用`-u`选项指定一个默认主机，这样后面就可以不加任何参数使用`git push`。
```
$ git push -u origin master
```

还有一种情况，就是不管是否存在对应的远程分支，将本地的所有分支都推送到远程主机，这时需要使用`--all`选项。
```
$ git push --all origin
```

如果远程主机的版本比本地版本更新，推送时Git会报错，要求先在本地做git pull合并差异，然后再推送到远程主机。这时，如果你一定要推送，可以使用--force选项。
```
$ git push --force origin
```


## config

配置 git

### 语法
```Bash
git config [<file-option>] [type] [--show-origin] [-z|--null] name [value [value_regex]]
git config [<file-option>] [type] --add name value
git config [<file-option>] [type] --replace-all name value [value_regex]
git config [<file-option>] [type] [--show-origin] [-z|--null] --get name [value_regex]
git config [<file-option>] [type] [--show-origin] [-z|--null] --get-all name [value_regex]
git config [<file-option>] [type] [--show-origin] [-z|--null] [--name-only] --get-regexp name_regex [value_regex]
git config [<file-option>] [type] [-z|--null] --get-urlmatch name URL
git config [<file-option>] --unset name [value_regex]
git config [<file-option>] --unset-all name [value_regex]
git config [<file-option>] --rename-section old_name new_name
git config [<file-option>] --remove-section name
git config [<file-option>] [--show-origin] [-z|--null] [--name-only] -l | --list
git config [<file-option>] --get-color name [default]
git config [<file-option>] --get-colorbool name [stdout-is-tty]
git config [<file-option>] -e | --edit
```

### 实例

我们知道我们执行的一些Git命令其实操作很频繁的类似有：

```
git status
git add
git commit
git push
git checkout
git branch
```

这些操作非常频繁，每次都要输入完全是不是有点麻烦，有没有一种简单的缩写输入呢？比如我对应的直接输入以下：

```
git status      =>    git s
git add         =>    git a
git commit      =>    git c
git push        =>    git p
git checkout    =>    git co
git branch      =>    git br
```

对应配置如下:

```
git config --global alias.s status
git config --global alias.a add
git config --global alias.c commit
git config --global alias.p push
```

当然以上别名不是固定的，你完全可以根据自己的习惯去定制，除此之外还可以设置组合，比如：

```
git push origin master  =>  git pom
```

对应配置如下:

```
git config --global alias.pom 'push origin master'
```
