---
layout: post
title: 在樹莓派上安裝 Home Assistant
categories: [Home Assistant]
tags: [Tech., Home Assistant]
description: 在樹莓派上安裝 Home Assistant
keywords: Home Assistant,HA,智能家居,智能居家,居家自動化
image:
  path: /images/posts/HomeAssistant/install/banner2.jpg
  alt: 示意圖
---

# 使用樹莓派來安裝 Home Assistant
首先可參考官方說明文件: [https://www.home-assistant.io/installation/raspberrypi](https://www.home-assistant.io/installation/raspberrypi)

過程相當的容易，當然手邊需要先準備的硬體除了你的 Raspberry Pi 之外，還需要有一張 Micro SD Card，以及讀卡機

以下就帶各位來走一遍安裝的流程

# 第一步 使用 Balena Etcher 把 HASSIO 寫到你的 Micro SD 卡
到官方下載位置: [https://www.balena.io/etcher](https://www.balena.io/etcher)

下載後執行，並選擇 Flash From URL

![Balena Etcher - Flash From URL](/images/posts/HomeAssistant/install/1.png)


# 第二步 參考Home Assistant 官方文件中的映象檔位置
因為我使用的是 Raspberry Pi 4，並且推薦大家安裝 64 bit 的版本，避免某件套件不支援的問題

我使用的 URL 是:

https://github.com/home-assistant/operating-system/releases/download/7.6/haos_rpi4-64-7.6.img.xz

(各位請依自已實際的情況使用)

在 Use Image URL 中填入上述的HASSIO 映象檔網址，然後按下 OK

![Balena Etcher - Use Image URL](/images/posts/HomeAssistant/install/2.png)


# 第三步 選擇你要寫入的 Micro SD Card
勾選你要寫入的媒體，按下 Select按鈕

這邊要留意一下，Micro SD Card 的內容會被清空

![Balena Etcher - Select Media](/images/posts/HomeAssistant/install/3.png)

# 第四步 執行 Flash!
按下 Flash! ，就會開始把映象檔寫入 Micro SD Card

![Balena Etcher - Flash](/images/posts/HomeAssistant/install/4.png)

# 第五步 等待寫入
Balena Etcher 開始寫入映象檔到你的 Micro SD Card ，這邊只需要等待他寫完後

出現 Flash Complete 的畫面就完成了!

![Balena Etcher - Waiting](/images/posts/HomeAssistant/install/5.png)


最後把 Micro SD Card 裝到樹莓派上開機

過一段時間後使用瀏覽器訪問以下位置:

[http://homeassistant.local:8123/](http://homeassistant.local:8123/)

就可以看到安裝好的 Home Assistant 囉!!

