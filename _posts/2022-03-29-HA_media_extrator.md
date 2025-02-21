---
layout: post
title: 在 Home Assistant 中使用 media_extrator  播放 youtube 直播影片
categories: [Apple,Home Assistant]
tags: [Tech., Home Assistant]
description: TestFlight 無法增加內部測試群組到建置版本
keywords: Apple, TestFlight, App, Store, Home Assistant,HA,media_extrator,youtube,chromecast,智能家居,智能居家,居家自動化
---

## 使用 media_extrator  播放 youtube 直播影片

若是要使用支援 Chromecast 的 media_player 播放 Youtube 指定的影片的話

我們可以使用Home Assistan 官方的 media_extrator 整合

<a href="https://www.home-assistant.io/integrations/media_extractor/" target="_blank">https://www.home-assistant.io/integrations/media_extractor/</a>

使用方式如下:

```yaml
service: media_extractor.play_media
data:
  media_content_type: MUSIC
  media_content_id: https://www.youtube.com/watch?v=AWKzr6n0ea0
target:
  entity_id: media_player.smart_tv
```

但若是 Youtube 影片是直播的，就沒辦法使用這個方式播放

可以改為使用 media_player.play_media 的方式播放:

```yaml
service: media_player.play_media
target:
  entity_id: media_player.smart_tv
data:
  media_content_type: cast
  media_content_id: ' { "app_name": "youtube", "media_id": "2mCSYvcfhtc" }'
```

其中 media_id 使用 youtube 影片網址中的 v 參數

例如: 

TVBS 新聞直播的網址為 [https://www.youtube.com/watch?v=2mCSYvcfhtc](https://www.youtube.com/watch?v=2mCSYvcfhtc)

media_id 則填入 2mCSYvcfhtc
