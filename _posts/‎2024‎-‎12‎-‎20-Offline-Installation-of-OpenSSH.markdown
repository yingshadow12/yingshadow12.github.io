---
layout:     post
title:      "离线安装Openssh"
date:       ‎2024‎-‎12‎-‎20 ‏‎14:33:58
author:     "yingshadow12"
tags:
    - Openssh
    - ssh
---
# Openssh离线安装教程
直接下载相关的离线安装包，https://github.com/PowerShell/Win32-OpenSSH/releases/latest

解压到`C:\Program Files\OpenSSH\` 目录下，注意只要文件，不要还有文件夹

![alt text](img/in-post/post/%E2%80%8E2024%E2%80%8E-%E2%80%8E12%E2%80%8E-%E2%80%8E20-Offline-Installation-of-OpenSSH/e5ee5a04d3b5e9f81938b1459117b4dd.png "Title")

在当前目录打开***管理员powershell***输入
```powershell
powershell.exe -ExecutionPolicy Bypass -File install-sshd.ps1
```
![alt text](img/in-post/post/%E2%80%8E2024%E2%80%8E-%E2%80%8E12%E2%80%8E-%E2%80%8E20-Offline-Installation-of-OpenSSH/f4203e7c59fc07740fcd7584d0904bdc.png "Title")

现在启动ssh服务
```powershell
net start sshd
```

![alt text](img/in-post/post/%E2%80%8E2024%E2%80%8E-%E2%80%8E12%E2%80%8E-%E2%80%8E20-Offline-Installation-of-OpenSSH/ed93ae440ab90e391743be36546077c7.png "Title")

最后可以自动启动下ssh服务，这样就不用重启后再手动启动ssh了
```powershell
Set-Service sshd -StartupType Automatic
```

为 sshd.exe 打开防火墙以允许入站 SSH 连接
```powershell
New-NetFirewallRule -Name sshd -DisplayName 'OpenSSH Server (sshd)' -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22
```


## 参考文档:<br>
[Win10 离线安装Openssh_openssh-win64.zip-CSDN博客](https://blog.csdn.net/marwenx/article/details/106096790)<br>
[Win32-OpenSSH_wiki](https://github.com/PowerShell/Win32-OpenSSH/wiki/Install-Win32-OpenSSH)

## 其他:<br>
[ssh配置教程](https://github.com/yingshadow12/yingshadow12.github.io/blob/master/_posts/2024%E2%80%8E-%E2%80%8E12%E2%80%8E-21-ssh-Configuration%20Tutorial.md)

## 转载来自:[Win10 离线安装Openssh_openssh-win64.zip-CSDN博客](https://blog.csdn.net/marwenx/article/details/106096790)
