---
layout: wiki
title: Git
categories: Git
description: Git 常用操作記錄。
keywords: Git, 版本控製
---

# 下載 Repository ( Clone )

```bash
git clone https://github.com/bensoncho/MyComponent.git
```

# 查看 Repository 狀態(是否有新增檔案/修改)

先切換到該Repo目錄後，執行以下命令

```bash
git status
```

# 加入修改過的檔案 ( Add )

## 加入單筆

```bash
git add test.txt
```

## 加入多筆

要注意的是，很容易把不相關的檔案也加進去

```bash
git add .
```

```bash
git add --all
```

# 刪除檔案

```bash
git rm test.txt
```

# 送交 ( Commit )

-m 為必要的參數，代表 commit 的說明訊息

```bash
git commit -m "commit message : add file test.txt "
```

# 將遠端的資料同步到本地

```bash
git pull
```

# 將本地的資料同步到遠端

```bash
git push
```

# 查詢遠端位置

```bash
git remote -v
```

# Log 查詢

可查詢所有版本管理執行過的記錄，包含修改人、修改時間、修改序號、修改內容...等資訊

```bash
git log
```

# 切換並建立到Branch

建立名為 dev 的 branch

```sql
git checkout -b dev
```

# 切換 Branch

```sql
git checkout dev
```

# 切換到遠端 Branch

```bash
git fetch origin dev
```

# 本地分支追蹤遠端分支

```bash
git push -u origin dev
```

追蹤後在cmder會顯示為 ( dev→ origin )  

git push 的時候會自動 push  到遠端 

另一個追蹤遠端分支的方式

git branch --set-upstream-to=origin/遠端分支名稱 本地分支名稱

```bash
git branch --set-upstream-to=origin/master master
```

# 刪除分支

```bash
git branch -D dev
```

# 刪除遠端分支

```bash
git push origin :dev
```

## 常用命令

| 功能                      | 命令                                  |
|:--------------------------|:--------------------------------------|
| 添加文件/更改到暫存區     | git add filename                      |
| 添加所有文件/更改到暫存區 | git add .                             |
| 提交                      | git commit -m msg                     |
| 從遠程倉庫拉取最新代碼    | git pull origin master                |
| 推送到遠程倉庫            | git push origin master                |
| 檢視配置信息              | git config --list                     |
| 檢視文件列錶              | git ls-files                          |
| 比較工作區和暫存區        | git diff                              |
| 比較暫存區和版本庫        | git diff --cached                     |
| 比較工作區和版本庫        | git diff HEAD                         |
| 從暫存區移除文件          | git reset HEAD filename               |
| 檢視在地遠程倉庫配置      | git remote -v                         |
| 回滾                      | git reset --hard 提交SHA              |
| 強製推送到遠程倉庫        | git push -f origin master             |
| 修改上次 commit           | git commit --amend                    |
| 推送 tags 到遠程倉庫      | git push --tags                       |
| 推送單個 tag 到遠程倉庫   | git push origin [tagname]             |
| 刪除遠程分支              | git push origin --delete [branchName] |
| 遠程空分支（等同於刪除）  | git push origin :[branchName]         |
| 檢視所有分支曆史          | gitk --all                            |
| 按日期排序顯示曆史        | gitk --date-order                     |