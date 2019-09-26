---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.trackInlineStats

 會判斷 ClickMap 資料是否已收集。

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | ClickMap | False |

## 語法和可能的值

```
js
s.trackInlineStats=true|false
```

*`trackInlineStats`變數應為 'true' 或 'false'。*

## 範例

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## 組態設定

無