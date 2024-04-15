---
layout: post
title: 安裝 TA-Lib
categories: Python
tags: [Tech.]
description: windows 及 linux 下安裝 TA-Lib
keywords: TA-Lib, talib, python
---

# TA-Lib 安裝

# Windows 系統下安裝

## 安裝 wheel 套件

```bash
pip install wheel
```

## 安裝 c++ 編譯環境太龐大，可以依python版本下載 whl 來安裝 ta-lib ，以 python 3.8 為例

到 [https://www.lfd.uci.edu/~gohlke/pythonlibs/#ta-lib](https://www.lfd.uci.edu/~gohlke/pythonlibs/#ta-lib)  

下載  TA_Lib-0.4.18-cp38-cp38-win_amd64.whl (依作業系統版本下載)  
(其中 38 這個數字則依照 python 的版本選擇檔案下載)

```bash
pip3 install  TA_Lib-0.4.18-cp38-cp38-win_amd64.whl
```

參考網址: [http://yhhuang1966.blogspot.com/2018/05/python-ta-lib.html](http://yhhuang1966.blogspot.com/2018/05/python-ta-lib.html)

# Linux 系統下安裝 ( Deiban 為例 )

```bash
apt-get update
apt-get install build-essential
```

取得 ta-lib

```bash
wget http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz
```

解壓進入目錄

```bash
tar -zxvf ta-lib-0.4.0-src.tar.gz
cd ta-lib/
```

編譯安裝

```bash
./configure --prefix=/usr
make
make install
```

安裝 TA-Lib

```bash
pip install TA-Lib
```

系统配置

```bash
ldconfig
```
