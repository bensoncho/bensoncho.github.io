---
layout: post
title: Apple 驗證收據伺服器 (503) Service Unavailable !
categories: [C#, Apple]
tags: [Tech.]
description: IOS In-App purchase receipt validation issue
keywords: IOS, IAB, IAP, Billing, Receipt, Validate, Validation, issue, 503, server, Unavailable, C#, Polly, Apple
flow: true
---

當伺服器收到 Client 回傳的 In-App Billing 收據，準備送到 Apple 驗講伺服器驗收據時
居然收到 HTTP Status Code 503 (Service Unavailable) 的回應 ??

## 收據驗證流程
在實做 IOS In-App Purchase 的時候
其中一段流程是Client 在使用者付費完成後，取得來自 Apple 的收據
這時通常 Client 會把收據送到自家的 Server 端, 再由 Server 端詢問 Apple 的驗證伺服器，這張收據是否有效，若有效的話, 則依使用者購買內容，提供使用者對應的服務
大致上流程如下圖:

```flow
st=>start: 付費完成
e=>end: 結束
op1=>operation: 取得收據
sub1=>subroutine: 其它資料處理
cond=>condition: Apple驗證伺服器
io=>inputoutput: 提供使用者對應服務

st->op1->cond
cond(yes)->io->e
cond(no)->sub1(right)->e
```

聽起來一切都很單純美好，罷特!!!
長時間以來，當去詢間 Apple 的驗證伺服器的時候，時不時就會遇到 HTTP Status Code 503 (Service Unavailable) 的回應，導致於當下無法判斷該購買是否有效，而無法立即提供使用者對應的服務!

## 解決方案
根據以往的經驗，發現獲得 HTTP Status Code 503 的狀況並不會長時間的持續，通常是短暫的服務中止，也就是瞬斷，因此想法是在發出 HttpWebRequest 的時候加入重試的機制

## 使用 Polly 實現重試的機制
Polly 為 .Net Foundation 中的 Open Source 類別庫, 可以協助我們處理類似的情況，安裝方式很簡單，透過 Nuget 套件管理員安裝即可
![pic1](/images/posts/CSharp/polly.png)


安裝完成後，我們簡單寫一段 Code 來測試
使用 Polly 來處理 WebException，當發生異常時，進行 Wait And Retry
直到成功或是重試次數達到上限

```C#
    //定義重試的時間間隔及次數
    TimeSpan[] retryTimes = new[] {
            TimeSpan.FromSeconds(1),
            TimeSpan.FromSeconds(2),
            TimeSpan.FromSeconds(3)
    };

    //定義 Policy,要 Handle 的 Exception 以及行為
    var policy = Policy
    .Handle<WebException>()
    .WaitAndRetry(retryTimes, (exception, ts, retryCount, context) =>
    {
        var response = ((WebException)exception).Response as HttpWebResponse;
        string StatusCodeString = string.Empty;
        int StatusCode = 0;
        if (response != null)
        {
            StatusCodeString = response.StatusCode.ToString();
            StatusCode = (int)response.StatusCode;
        }
        string exMessage = exception.Message;
        string errMsg = $"Http StatusCode: {StatusCode.ToString()} {StatusCodeString}, Enter ReTry: {retryCount}";
        Response.Write($"{errMsg} <BR> ");
        Response.Flush();
    });    

    //進行測試
    string fake_url = "https://graph.facebook.com/v2.10/123/ids_for_apps";
    try
    {
        string result = policy.Execute(() =>
            some_httpwebrequest_function(fake_url);
        );
        Response.Write($"Result: {result} <BR>");
    }
    catch (Exception ex)
    {
        Response.Write(ex.Message);
    }
    Response.Write("Finish");
```

結果如下:

![pic2](/images/posts/CSharp/polly_result.png)


參考:
[https://dotnetfoundation.org/projects/polly](https://dotnetfoundation.org/projects/polly)
