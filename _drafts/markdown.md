---
layout: wiki
title: Markdown
categories: Markdown
description: Markdown 常用文法示例。
keywords: Markdown
mermaid: true
sequence: true
flow: true
mathjax: true
mindmap: true
---

**目錄**

* TOC
{:toc}

### 超連結

```
[靠譜-ing](https://mazhuang.org)

<https://mazhuang.org>
```

[靠譜-ing](https://mazhuang.org)  

<https://mazhuang.org>

### 列表

```
1. 有序列表項 1

2. 有序列表項 2

3. 有序列表項 3
```

1. 有序列表項 1

2. 有序列表項 2

3. 有序列表項 3

```
* 無序列表項 1

* 無序列表項 2

* 無序列表項 3
```

* 無序列表項 1

* 無序列表項 2

* 無序列表項 3

```
- [x] 任務列表 1
- [ ] 任務列表 2
```

- [x] 任務列表 1
- [ ] 任務列表 2

### 強調

```
~~刪除線~~

**加黑**

*斜體*
```

~~刪除線~~

**加黑**

*斜體*

### 標題

```
# 一級標題
## 二級標題
### 三級標題
#### 四級標題
##### 五級標題
###### 六級標題
```

Tips: `#` 與標題中間要加空格。

### 錶格

```
| HEADER1 | HEADER2 | HEADER3 | HEADER4 |
| ------- | :------ | :-----: | ------: |
| content | content | content | content |
```

| HEADER1 | HEADER2 | HEADER3 | HEADER4 |
| ------- | :------ | :-----: | ------: |
| content | content | content | content |

1. :----- 錶示左對齊
2. :----: 錶示中對齊
3. -----: 錶示右對齊

### 代碼塊

```python
print 'Hello, World!'
```

1. list item1

2. list item2

   ```python
   print 'hello'
   ```

### 圖片

```
![本站favicon](/favicon.ico)
```

![本站favicon](/favicon.ico)

### 錨點

```
* [目錄](#目錄)
```

* [目錄](#目錄)

### Inline Attribute

Span Inline Attribute 詳情參考 <https://kramdown.gettalong.org/syntax.html#span-ials>

Block Inline Attribute 詳情參考 <https://kramdown.gettalong.org/syntax.html#block-ials>

給塊/元素添加 class、id、內嵌樣式等：

```
![本站favicon](/favicon.ico){:.center}

Hello, *world*{:#world} 

Hello, *world*{: style="color:red"} 
```

![本站favicon](/favicon.ico){:.center}

Hello, *world*{:#world} 

Hello, *world*{: style="color:red"} 

結合自定義的樣式，有些場景比較有用。

### Emoji

:camel:
:blush:
:smile:

### Footnotes

This is a text with footnote[^1].

### mermaid

<div class="mermaid">
sequenceDiagram
    Alice-->>John: Hello John, how are you?
    John-->>Alice: Great!
</div>

### sequence

```sequence
Andrew->China: Says Hello
Note right of China: China thinks\nabout it
China-->Andrew: How are you?
Andrew->>China: I am good thanks!
```

### flowchart

```flow
st=>start: Start
e=>end
op1=>operation: My Operation
sub1=>subroutine: My Subroutine
cond=>condition: Yes
or No?
io=>inputoutput: catch something...

st->op1->cond
cond(yes)->io->e
cond(no)->sub1(right)->op1
```

### mathjax

When $$(a \ne 0)$$, there are two solutions to $$(ax^2 + bx + c = 0)$$ and they are

$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$

### mindmap

```mindmap
# topic
## topic2
### topic2.1
### topic2.2
## topic3
<!--Note-->
這是一個備註
<!--/Note-->
### topic3.1
### topic3.2
#### topic3.2.1
#### topic3.2.2
#### topic3.2.3
#### topic3.2.4
#### topic3.2.5
### topic3.4
### topic3.5
### topic3.6
```

[^1]: Here is the footnote 1 definition.
