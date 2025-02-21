---
layout: post
title: 使用 VSCode 建置 Python 開發環境
categories: [Python, VSCode]
tags: [Tech.]
description: 使用 VisualStudio Code 建置 Python 開發環境
keywords: Python, VSCode
---

VSCode 是近來最熱門的程式編輯器之一
本篇文章介紹如何使用它來打造 Python的開發環境

# 安裝 Python 的擴充功能

隨意打開一個 Python 檔案，或是到 Extensions 介面，搜尋 Python 然後下載

![Python Extention](/images/posts/VSCode/python_extension.jpg)

# 設定工作執行器

請按下「Ctrl+ Shift + P」(OS X 為 CMD + SHIFT + P) 打開 Command Palette

請搜尋「task」並選擇「工作: 設定工作執行器 (Tasks: Configure Task )  → Create  tasks.json file from template → Others」

# 設定 Tasks.json 檔案

```json
{ 
    // See https://go.microsoft.com/fwlink/?LinkId=733558 
    // for the documentation about the tasks.json format 
    "version": "2.0.0", 
    "tasks": [ 
        {   
            "label": "Python", 
            "type": "shell", 
            "command": "python", 
            "args": [ "${file}" ], 
            "presentation": { 
                "reveal": "always", 
                "panel": "shared" 
            }, 
            "group": { 
                "kind": "build", 
                "isDefault": true 
            } 
        } 
    ] 
}
```

# 執行

到這邊就可以開始執行囉！請按 Ctrl+ Shift + B ( OS X：CMD + SHIFT + B) 來執行程式，結果會輸出於下方。

![Python Result](/images/posts/VSCode/python_result.png)
