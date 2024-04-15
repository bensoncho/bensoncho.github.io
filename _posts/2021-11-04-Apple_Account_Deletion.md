---
layout: post
title: 2022/1/31 開始，所有申請上架到 App Store 的 App 或是現有 App 的更新，必需要提供使用者刪除帳號的方法
categories: [Apple]
tags: [Tech.]
description: 從App內啟動刪除帳號
keywords: IOS, Apple, account, deletion, apps, app
---

## Apple 要求開發者必需提供從 App 內啟動刪除帳號的方式
Apple 在 2021/10/6 的時候，在 Developer 網站公告了一則新聞  
主要是要求開發者在 2022/1/31 開始，所有申請上架到 App Store App (或現有 App 的更版)  
參考: <a href="https://developer.apple.com/news/?id=mdkbobfo" target="_blank">https://developer.apple.com/news/?id=mdkbobfo</a>

如果在 iOS、iPadOS 或 macOS 的 App 提供使用者建立帳號的話，同時也必需要有提供使用者刪除帳號的方法。  
但是光是這個訊息實在是有些模糊  
App 常用的登入渠道包含 Facebook登入、Google登入、或是 Facebook 登入，這類第三方登入的管道  
大部份 App 是以帳號綁定的概念，與後端的使用者 ID 做連結，這樣算不算是 "允許使用者建立帳號" 呢？(搞的我好亂啊..)  
Developer Forums 似乎也有開發者在提問相關的訊息，但目前看到相關的訊息都尚未得到 Apple 的回覆  
<a href="https://developer.apple.com/forums/thread/691899" target="_blank">https://developer.apple.com/forums/thread/691899</a>


從 engadget 這邊的見解可以看到，或許在 App 內，提供一個按鈕導向外部的網站  
，或是甚至導向與服務人員聯絡 都符合準則。
若是 App 有心要留下使用者，還是有很大的操作空間。


## 資源

<a href="https://developer.apple.com/news/?id=mdkbobfo" target="_blank">Account deletion within apps required starting January 31</a>  
<a href="https://www.engadget.com/apple-app-store-ios-developers-delete-account-report-193119525.html">Apple says apps must offer a way to delete your account starting in early 2022</a>  
<a href="https://developer.apple.com/forums/thread/691899">Account deletion within apps required (Apple developer forums)</a>
<a href="https://developer.apple.com/forums/thread/683386">App Store Review Guideline 5.1.1(v): Question about account deletion.(Apple developer forums)</a>
<a href="https://developer.apple.com/forums/thread/674661">Sign in with Apple and backend account deletion(Apple developer forums)</a>

