---
layout:     post
title:      "FFmpeg 安装指南"
date:       ‎2025‎-0‎1‎-0‎3 ‏‎22:09:18
author:     "yingshadow12"
header-style: text
catalog:    true
tags:
    - FFmpeg
    - 配置
    - 安装指南
    - 教程
---
# FFmpeg 安装指南

FFmpeg 是一个开源的多媒体框架，能够处理视频和音频数据。以下是在不同操作系统上安装 FFmpeg 的步骤。

## Windows

### 使用 Chocolatey

如果你使用的是 Windows 系统，可以通过 Chocolatey 包管理器来安装 FFmpeg。

1. 打开 PowerShell 作为管理员。
2. 运行以下命令来安装 Chocolatey（如果你还没有安装）：
   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force;
   [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072;
   iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
   ```
3. 安装 FFmpeg：
   ```powershell
   choco install ffmpeg
   ```

### 手动安装

1. 访问 FFmpeg 官方网站下载页面：[FFmpeg Download](https://ffmpeg.org/download.html)
2. 下载适用于 Windows 的静态构建版本。
![alt text](image-1.png)
在打开的新页面中，选择适合你的系统的版本。
![alt text](image-2.png)
>ffmpeg-master-latest-win64-gpl-shared.zip:<br>
Shared: 这个版本是动态链接库（DLL）版本，意味着它依赖于运行时的外部库。这通常意味着文件大小较小，但是你需要确保运行FFmpeg的系统上有相应的DLL文件

>ffmpeg-master-latest-win64-gpl.zip:<br>
GPL: 同样，这个版本也是在GPL许可证下发布的。
没有“shared”这个后缀，这通常意味着这是一个静态链接库（Static Library）版本，它不依赖于外部的DLL文件。这种版本通常文件较大，因为它包含了所有必要的代码和资源。
3. 解压缩下载的文件到你选择的目录。
4. 将 FFmpeg 的 `bin` 目录添加到你的系统环境变量中。
<!-- 
## macOS

### 使用 Homebrew

如果你使用的是 macOS，可以通过 Homebrew 来安装 FFmpeg。

1. 打开终端。
2. 安装 Homebrew（如果你还没有安装）：
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
3. 安装 FFmpeg：
   ```bash
   brew install ffmpeg
   ```

### 手动安装

1. 访问 FFmpeg 官方网站下载页面：[FFmpeg Download](https://ffmpeg.org/download.html)
2. 下载适用于 macOS 的静态构建版本。
3. 解压缩下载的文件到 `/usr/local/bin` 或者你选择的目录。

## Linux

### 使用包管理器

大多数 Linux 发行版都可以通过其包管理器安装 FFmpeg。

对于基于 Debian/Ubuntu 的系统：
```bash
sudo apt update
sudo apt install ffmpeg
```

对于基于 Fedora 的系统：
```bash
sudo dnf install ffmpeg
```

对于基于 Arch 的系统：
```bash
sudo pacman -S ffmpeg
```

### 手动安装

1. 访问 FFmpeg 官方网站下载页面：[FFmpeg Download](https://ffmpeg.org/download.html)
2. 下载适用于 Linux 的源代码。
3. 解压缩下载的文件。
4. 按照提供的 `INSTALL` 文件中的说明进行编译和安装。--> 

## 验证安装

在任何操作系统上，你可以通过在终端或命令提示符中运行以下命令来验证 FFmpeg 是否安装成功：

```bash
ffmpeg -version
```

如果 FFmpeg 已正确安装，你将看到版本信息和其他相关细节。
