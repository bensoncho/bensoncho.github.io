---
layout: wiki
title: Docker
categories: Docker 
description: Docker 常用操作記指令
keywords: Docker
---

# 常用指令

# 查看映像檔

```docker
docker images
```

# 下載docker images

```docker
docker pull benson818/anaconda:2.0
```

# 執行映像檔

-d : 背景執行 

--name : 給Container名稱比較好操作 

-p:指定 host 的port對應到docker的port 

-v:將 D:\\JoybombAPILog 路徑對應到 Docker 裡的 /Log/，讓 Docker 可以有地方寫 Log

```docker
Docker run -d --name joybombapicore -p 80:5000 -v D:\\JoybombAPILog:/Log/ joybombapicore
```

# 進入 docker bash

```docker
docker exec -it joybombapicore /bin/bash
```

# 離開docker

```docker
exit
```

# 查看在執行中的Container

```docker
docker ps
```

# 開始 Container

```docker
docker start  [ContainerID or ContainerName]
```

# 停止 Container

```docker
docker stop [ContainerID or ContainerName]
```

# 查看所有的Container

```docker
docker ps -a
```

# 移除Container

```docker
docker rm  [ContainerID or ContainerName]
```

# 移除docker images

```docker
docker rmi [ImagesID or ImageName]
```

# 登入docker hub

```docker
docker login
```

# 替docker image 加上tag

把 joybombapicore 新增一個名為 benson818/joybombapicore 的 images

```docker
docker tag joybombapicore  benson818/joybombapicore
```

# 把image上傳到docker hub

```docker
docker push benson818/joybombapicore:1.3
docker push benson818/joybombapicore:latest
```

# 從docker hub下載映像檔

預設會抓標籤 latest

```docker
docker pull benson818/joybombapicore
```

# 儲存映像檔

```docker
docker save -o joybombapicore.tar benson818/joybombapicore
```

# 載入映像檔

```docker
docker load < joybombapicore.tar
```

# 使用目前的Container建立Images

-m 訊息

-a 作者

```docker
docker commit -m "Add Tensorflow / Keras" -a "Benson" anaconda benson818/anaconda:1.0
```

# 把 images 上傳到 Docker Hub

```docker
docker push benson818/anaconda:1.0
```
