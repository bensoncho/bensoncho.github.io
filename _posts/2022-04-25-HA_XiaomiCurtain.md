---
layout: post
title: Home Assistant 使用 Gateway3 串接米家多功能網關2 (小米智能多模網關)
categories: [Home Assistant]
tags: [Tech., Home Assistant]
description: Home Assistant 串接米家多功能網關2 (小米智能多模網關)
keywords: Home Assistant,HA,Xiaomi,gateway3,智能家居,智能居家,居家自動化,小米多模網關,米家多功能網關2
image:
  path: /images/posts/HA_XiaomiCurtain/xiaomi-gateway-3.png
  alt: 小米智能多模網關
---

# 使用 Gateway3 串接米家多功能網關2 (小米智能多模網關)

## 我們要使用到的套件為 Gateway3 
首先要先確認網關的韌體版本，是否有在支援的列表中

Github 位置: [https://github.com/AlexxIT/XiaomiGateway3#supported-firmwares](https://github.com/AlexxIT/XiaomiGateway3#supported-firmwares)

目前筆者手中拿到的網關韌體版本為 v1.5.0_0026


# 第一步，安裝 Xiaomi Gateway 3 整合
到 Home Assistant 中的設定-> 整合， 新增整合，尋找 Xiaomi Gateway 3
點擊後再選擇 Mi Cloud Account，輸入小米帳密後送出


# 第二步 添加網關

重覆新再新增 Xiaomi Gateway 3 整合，這次應該可以看到網關出現在列表中
選擇網關， Telnet指令，請參考這裡
[https://gist.github.com/zvldz/1bd6b21539f84339c218f9427e022709](https://gist.github.com/zvldz/1bd6b21539f84339c218f9427e022709)


筆者使用的韌體版本 v1.5.0_0026，使用以下指令即可成功接入
```yaml
{"method":"set_ip_info","params":{"ssid":"\"\"","pswd":"123123 ; passwd -d admin ; echo enable > /sys/class/tty/tty/enable; telnetd"}}
```

完成後便可看到網關還有網關下的子設備了!
