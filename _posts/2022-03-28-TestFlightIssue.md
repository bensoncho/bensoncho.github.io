---
layout: post
title: App Store Connect - TestFlight 無法增加內部測試群組到建置版本
categories: [Apple]
tags: [Tech.]
description: TestFlight 無法增加內部測試群組到建置版本
keywords: Apple, TestFlight, App, Store
---

## TestFlight 無法增加內部測試群組到建置版本
上週五半夜，突然收到 PM 的 OnCall，網路的那端著急的說
IOS App 的版本是上傳完成了，但一直無法進行 TestFlight 測試
原因是無法在新的建置的版本中，加入內部測試群組
查看了一下 App Store Connect 後台，TestFlight 中嘗試加入內部群組的地方是反灰無法選擇的 (只能加入外部群組)
而直接進入內部測試群組中，也沒辦法加入建置的版本
另外在 TestFlight 的 Client 端，也確實沒辦法看到該 App 的新版本!
即使手動發送邀請測試人員，也沒辦收到通知。

### App Store Connect 自動加入內部測試群組，需等待時間
經過爬文發現，新的建置版本 在 App Store Connect 後台應該是已經自動加入了內部沒試群組，只是需要一段等待時間，如果等待時間太久，可以考慮再 Submit 一個新的版號去重新觸發 App Store Connect 後台的流程!

而正當我們打算再上一個新的 build 的時候，在新建置版中的測試群組自動出現了內部測試群組了!
PS: 當天我們上傳新版本後，待等了約 3.5 個小時，才從 TestFlight中看到自動被加入的內部測試群組...

