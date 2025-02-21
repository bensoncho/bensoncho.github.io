---
layout: post
title: Matplotlib 中文亂碼解決
categories: Python
tags: [Tech.]
description: Matplotlib 中文亂碼解決
keywords: Python, matplotlib
---

Matplotlib 是 Python 中很好用的一個繪圖 Package，但原生並不支援中文
可透過加入並指定中文字型，使其可正確顯示中文 
方式如下: 

# 找到中文的字體檔(ttf/otf)

由Google與Adobe一同推出的 **思源黑體(Noto Sans CJK TC)** 與 **思源宋體(Noto Serif CJK TC)。** 可以到 **[Google Noto Fonts](https://www.google.com/get/noto/)** 來下載，搜尋 ”Traditional Chinese” 就可以找到，如下圖。

# 將字體放到matplotlib的字體套件資料夾

使用以下指令查詢安裝路徑

```python
import matplotlib
print(matplotlib.__file__)
```

出現位置:  /opt/conda/lib/python3.7/site-packages/matplotlib/**init**.py

/opt/conda/lib/python3.7/site-packages/matplotlib 即為安裝路徑

# 將字型檔複製到 matplotlib\mpl-data\fonts\ttf

接著打開剛剛下載的字體壓縮檔，你會發現許多個字體檔，只要選擇一個順眼的字體丟到matplotlib\mpl-data\fonts\ttf即可。

# 刪除當前使用者matplotlib 的緩衝檔案

```bash
$cd ~/.cache/matplotlib
$rm -rf *.*
```
 
# 程式中調整字型

```bash
import matplotlib.pyplot as plt
plt.rcParams['font.sans-serif']=['SimHei'] #用來正常顯示中文標籤
plt.rcParams['axes.unicode_minus']=False #用來正常顯示負号
plt.title(u'中文測試')  #這裡的 u 最好不要省略
```

參考:

[如何在Win 10解決matplotlib中文顯示的問題?](https://daxpowerbi.com/%E5%A6%82%E4%BD%95%E5%9C%A8win-10%E8%A7%A3%E6%B1%BAmatplotlib%E4%B8%AD%E6%96%87%E9%A1%AF%E7%A4%BA%E7%9A%84%E5%95%8F%E9%A1%8C/)

[ubuntu系統下matplotlib中文亂碼問題的解決方法](https://codertw.com/%E4%BC%BA%E6%9C%8D%E5%99%A8/377520/)
