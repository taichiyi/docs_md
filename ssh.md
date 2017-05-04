<!-- ![logo](http://oop4q34sz.bkt.clouddn.com/128px-Tux.png) -->

# ssh

Secure Shell（缩写为SSH），由IETF的网络工作小组（Network Working Group）所制定；SSH为一项创建在应用层和传输层基础上的安全协议，为计算机上的Shell（壳层）提供安全的传输和使用环境。

传统的网络服务程序，如rsh、FTP、POP和Telnet其本质上都是不安全的；因为它们在网络上用明文传送数据、用户帐号和用户口令，很容易受到中间人（man-in-the-middle）攻击方式的攻击。就是存在另一个人或者一台机器冒充真正的服务器接收用户传给服务器的数据，然后再冒充用户把数据传给真正的服务器。

而SSH是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。利用SSH协议可以有效防止远程管理过程中的信息泄露问题。通过SSH可以对所有传输的数据进行加密，也能够防止DNS欺骗和IP欺骗。

SSH之另一项优点为其传输的数据可以是经过压缩的，所以可以加快传输的速度。SSH有很多功能，它既可以代替Telnet，又可以为FTP、POP、甚至为PPP提供一个安全的“通道”。

[ssh-keygen](#ssh-keygen) [ssh-agent](#ssh-agent) [ssh-add](#ssh-add) 

## ssh-keygen

### 语法

```Bash
ssh-keygen [-t <type>] [-b <length>] [-C <comment>] [-f <directory>]
```

- <type\>:
    - rsa1(SSH-1)
    - rsa(SSH-2)
    - dsa(SSH-2)
    - ecdsa(SSH-5)
- <length\>: 
    - 单位: bits
    - 指定密钥长度。对于RSA密钥，最小要求768位，默认是2048位。DSA密钥必须恰好是1024位(FIPS186-2 标准的要求)
- <comment\>: 
    - 注释
- <directory\>: 
    - 保存地址

### 实例

添加RSA密钥

```Bash
ssh-keygen -t rsa -f ~/.ssh/id_rsa_2 -C "taichiyi@foxmail.com"
```

## ssh-agent

`ssh-agent`是一种控制用来保存公钥身份验证所使用的私钥的程序，其实`ssh-agent`就是一个密钥管理器，运行`ssh-agent`以后，使用ssh-add将私钥交给`ssh-agent`保管，其他程序需要身份验证的时候可以将验证申请交给ssh-agent来完成整个认证过程。

### 实例
开启`ssh-agent`

```Bash
$ ssh-agent bash
```


## ssh-add

### 实例

添加密钥到`SSH agent`

```Bash
$ ssh-add ~/.ssh/id_rsa
```

查看`SSH agent`的密钥列表

```Bash
$ ssh-add -l
```

## 管理多组密钥对

您可以创建 ~/.ssh/config 来管理多组密钥对，每一个 SSH 服务器对应一组密钥对。或者，您甚至可以对所有的 SSH 服务器使用同一组密钥对。不过如果您觉得这样不合适，还是编辑配置文件：

### 实例
```Bash
# host1
Host github.com
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa

# host2
Host github.testyi
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa_2
```