---
layout: post
title: WSL(Windows Subsystem for Linux) 安裝與使用
categories: Windows
description: Windows Subsystem for Linux 安裝與使用
keywords: WSL, Subsystem, Linux
---

# WSL (Windows Subsystem for Linux) 安裝與使用

以系統管理員身分執行  Windows PowerShell

輸入以下指令

```bash
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

之後會詢問是否要重新開啟，輸入 Y 後重新開機

接著就可以到 Microsoft Store 安裝自己習慣使用的 Linux 版本

[https://aka.ms/wslstore](https://aka.ms/wslstore)

- [Ubuntu 16.04 LTS](https://www.microsoft.com/store/apps/9pjn388hp8c9)
- [Ubuntu 18.04 LTS](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
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