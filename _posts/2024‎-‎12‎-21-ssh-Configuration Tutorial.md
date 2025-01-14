---
layout:     post
title:      "ssh配置教程"
date:       2024‎-‎12‎-21‎ ‎14:33:55
author:     "yingshadow12"
header-style:text
catalog:    true
tags:
    - ssh配置
    - 教程
---
# SSH的配置密钥登陆
需要完成配置，首先完成OpenSSH Server的安装

[ 安装OpenSSH Server](https://blog.csdn.net/u010953609/article/details/123114938)里面详细写了在Windows Sever 2016部署的过程


## 启动服务
你需要知道如何启动和停止

``` powershell
# 启动服务
Start-Service sshd
```

``` powershell
# 停止服务
Stop-Service sshd
```

``` powershell
# 启动服务
net start sshd
```

``` powershell
# 停止服务
net stop sshd
```

## 启用密钥认证

用记事本(notepad)打开位于 ```%programdata%\ssh\sshd_config ```<br>
```notepad %programdata%\ssh\sshd_config```
的文件

找到 #PubkeyAuthentication yes ，去掉注释即可

## 生成密钥

``` powershell
ssh-keygen -t rsa -C "youremail@email.com" -f C:\Users\username/.ssh/<你想保存的密钥名>
```
## 放置公钥

阅读文档发现有这句话：
>AuthorizedKeysFile    授权密钥文件
<br>默认值为“.ssh/authorized_keys 
<br>.ssh/authorized_keys2”
<br> &ensp;&ensp; 如果路径不是绝对路径，则它相对于用户的主目录（或配置文件图像路径）。 示例： c:\users\user。
<br> &ensp;&ensp;  请注意，如果用户属于**管理员**组，则改为使用 %programdata%/ssh/administrators_authorized_keys


### 发现

用户属于**管理员**组，则改为使用
```%programdata%/ssh/administrators_authorized_keys```
而且文件名也必须是： ```administrators_authorized_keys```

### 放置

注意这是在用户属于**管理员**组的情况下的教程

把生成的公钥放到服务器上

在```%USERPROFILE%/.ssh/```中找出后缀名为```.pub```的文件

上传到服务器的```%programdata%/ssh/```文件夹

将文件重命名为```administrators_authorized_keys```就可以了

如果有多电脑连接同一账号的要求的话

使用```echo```命令+```.pub中内容```+>>```administrators_authorized_keys```
<br>如```echo ssh--rsa xxxxxxxxxxxxxxxxxx>>administrators_authorized_keys ```


## 部分摘抄来源:[ 安装OpenSSH Server](https://blog.csdn.net/u010953609/article/details/123114938)
