---
layout: post
title: WSL(Windows Subsystem for Linux) 安裝與使用
categories: Windows
tags: [Tech.]
description: Windows Subsystem for Linux 安裝與使用  
keywords: Windows, SubSystem, Linux
---

WSL 是適用於 Linux 的 Windows 子系統，可讓開發人員執行 GNU/Linux 環境 (包括大部分的命令列工具、公用程式和應用程式)，  
直接在 Windows 上執行，不需進行修改，不會造成傳統虛擬機器或 dualboot 設定的額外負荷。  

# WSL (Windows Subsystem for Linux) 安裝與使用

以系統管理員身分執行  Windows PowerShell

輸入以下指令

```bash
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

之後會詢問是否要重新開啟，輸入 Y 後重新開機

安裝 Linux Distro
安裝好 WSL 後，你只是安裝好了這個框架，仍然需要安裝一個可以用的 Linux 發行版（Linux Distribution，簡稱 Linux Distro)  
通常會建議直接安裝 Ubuntu LTS。  
接著可以到 Microsoft Store 安裝自己習慣使用的 Linux 版本

[https://aka.ms/wslstore](https://aka.ms/wslstore)

- [Ubuntu 18.04 LTS](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
- [Ubuntu 16.04 LTS](https://www.microsoft.com/store/apps/9pjn388hp8c9)
- [OpenSUSE Leap 15](https://www.microsoft.com/store/apps/9n1tb6fpvj8c)
- [OpenSUSE Leap 42](https://www.microsoft.com/store/apps/9njvjts82tjx)
- [SUSE Linux Enterprise Server 12](https://www.microsoft.com/store/apps/9p32mwbh6cns)
- [SUSE Linux Enterprise Server 15](https://www.microsoft.com/store/apps/9pmw35d7fnlx)
- [Kali Linux](https://www.microsoft.com/store/apps/9PKR34TNCV07)
- [Debian GNU/Linux](https://www.microsoft.com/store/apps/9MSVKQC78PK6)
- [適用于 WSL 的 Fedora Remix](https://www.microsoft.com/store/apps/9n6gdm4k2hnc)
- [Pengwin](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
- [Pengwin Enterprise](https://www.microsoft.com/store/apps/9N8LP0X93VCP)
- [Alpine WSL](https://www.microsoft.com/store/apps/9p804crf0395)

# 啟用 Linux Distro
安裝好後，即可在市集中啟用剛剛安裝的 Linux Distro  
第一次啟用時，會提示輸入使用者帳號及密碼
輸入後便完成啟用

# 查看 WSL 列表及版本
```bash
wsl -l -v
```

# 設定預設要使用的 Linux Distro
wslconfig /setdefault Name
範例: 
```bash
wslconfig /setdefault Ubuntu-18.04
```

# 如何在 WSL 中安裝套件?

在 linux 下安裝方式相同，使用該系統安裝指令就可以了

例如 ubuntu 的安裝方式:

```bash
apt-get install [package-name]
```

# 如何從 Powershell 直接轉換至 WSL 環境

直接輸入指令 wsl 便可

```bash
wsl
```

# 如何直接在 Windows PowerShell 中執行 linux 的指令?

```bash
wsl [command]
```

# 如何在 WSL 中存取 windows 系統中的檔案?

windows 的檔案系統會被 mount 在 /mnt/ 下，例如 D槽 就會是對應在 /mnt/d，可以到該路徑下使用

# WSL 中的檔案會存在 Windows 中的哪個位置?

WSL 系統中的檔案會存在下面路徑中 (其中的[****]會依據安裝的Linux系統版本而有所不同)

```bash
C:\Users\%UserName%\AppData\Local\Packages\CanonicalGroupLimited.[****]\LocalState\rootfs
```
