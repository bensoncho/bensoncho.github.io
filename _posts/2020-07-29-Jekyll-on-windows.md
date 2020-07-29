---
layout: post
title: 使用 Bash 在 Windows 上安裝 Jekyll
categories: [Windows, Jekyll]
description: 在 Windows 上安裝 Jekyll ( 必需啟用 Windows Subsystem for Linux )
keywords: Jekyll, Github, pages, gitpage, 網站產生器, 部落格
---

# 在 Windows 系統上安裝 jekyll

# 先決條件

You must have Windows Subsystem for Linux enabled.

# 開啟 CMD 並進入 bash

```bash
bash
```

# 更新 repo lists 及 packages

```bash
sudo apt-get update -y && sudo apt-get upgrade -y
```

# 從 BrightBox 的 Repository 安裝 Ruby

```bash
sudo apt-add-repository ppa:brightbox/ruby-ng
sudo apt-get update
sudo apt-get install ruby2.5 ruby2.5-dev build-essential dh-autoreconf
```

# 更新 Ruby gems

```bash
gem update
```

# 安裝 Jekyll

```bash
gem install jekyll bundler
```

( 這裡不需要使用 sudo ) 

# 確認是否安裝成功

```bash
jekyll -v
```


參考:

[https://jekyllrb.com/docs/installation/windows/](https://jekyllrb.com/docs/installation/windows/)
