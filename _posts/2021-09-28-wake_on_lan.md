---
layout: post
title: Windows 10 Wake on lan 遠端開機設置
categories: [Windows,Home Assistant]
tags: [Tech.]
description: Windows 10 Wake on lan 遠端開機設置
keywords: Windows, wake, on, lan, wakeonlan, magic, packet,Home Assistant,HA,智能家居,智能居家,居家自動化
---

因為家中有使用 Home Assistant 智慧居家的關係
順便把 Windows 開關機也設定為一個開關的實體
在設定 Wake On Lan 的時候，順便記錄一下過程


1.先安裝網卡驅動程式

2.從裝置管理員找到網卡，並進到進階設定，把 wake on lan 啟用，這裡的名稱可能會因為網卡的驅動程式而有不同

![網卡設定](/images/posts/windows/lan.png)

3.在控制台裡的電源選項中，取消勾選開機快速啟動

![電源設定](/images/posts/windows/power.png)

4.要讓內網其它裝置可以 Ping 的到要被喚醒的這台 Windows 電腦，到防火牆設置裡的輸入規則裡，把允許連線打勾

![Firewall設定](/images/posts/windows/firewall.png)


以上設定完成後
基本上就可以使用 Magic packet 來喚醒電腦了 
