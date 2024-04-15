---
layout: post
title: 將台版米家 LED 智慧燈泡 Lite 彩光版整合到 Home Assistant (使用陸版米家APP)
categories: [Home Assistant]
tags: [Tech., Home Assistant]
description: 將台版米家 LED 智慧燈泡 Lite 彩光版整合到 Home Assistant (使用陸版米家APP)
keywords: Home Assistant,HA,智能家居,智能居家,居家自動化,Yeelight,Color5, 米家, LED, 智慧燈泡, Lite, 彩光版
image:
  path: /images/posts/HomeAssistant/YeelightColor5/banner.jpg
  alt: 示意圖
---

# 台版米家 LED 智慧燈泡 Lite 彩光版整合到 HA
前陣子買了一個米家 LED 智慧燈泡 Lite 彩光版，一直遲遲未使用

最近來研究一下如何將它整合到 HA 中

目前我的米家 App使用地區是大陸伺服器

台版App ，可在新增裝置的地方，搜尋Yeelight 彩光燈泡後加入 (燈泡要先斷電、通電5次，看到彩色燈光後完成重置)

在米家 App 順利找到裝置，並且也看到了把資訊上傳到伺服器的畫面

但是回到裝置列表，找不到彩光燈泡這個裝置

我想應該是陸版伺服器把台版裝置隱藏起來了!!

這邊先不用理它，回到 HA 的整合，使用 MIIO 來找看看!

# 回到 HA 的整合
點選新增整合-> MIIO

![MIIO](/images/posts/HomeAssistant/YeelightColor5/miio.jpg)

輸入帳號密碼，選擇伺服器後按下傳送

從下拉選單中 應該可以找到 yeelink.light.color5 的裝置

![Yeelight](/images/posts/HomeAssistant/YeelightColor5/color5.jpg)

按下傳送後，可再看到裝置的ip、token等等資訊

把它記錄下來!

# 安裝 hass-miio-yeelink
接下來要使用到的是 hass-miio-yeelink 這個套件

[https://github.com/al-one/hass-miio-yeelink](https://github.com/al-one/hass-miio-yeelink)

可自行下載後放到 custome_components 的資料夾裡，並重啟 HA


# 設定 Miio for Yeelink
安裝好上述套件後，回到 HA 的整合 -> 新增整合

搜尋 Miio for Yeelink ，並輸入在 MIIO 取得的裝置資訊

按下傳送，便完成設定了!

![Miio for Yeelink](/images/posts/HomeAssistant/YeelightColor5/yeelink.jpg)

以上步驟完成，就可以在 HA 裡操作米家LED智慧燈泡Lite彩光版囉!

![Yeelink Color5](/images/posts/HomeAssistant/YeelightColor5/final.jpg)

