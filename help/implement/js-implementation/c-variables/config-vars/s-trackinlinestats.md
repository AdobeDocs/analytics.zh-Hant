---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.trackInlineStats

 會判斷 ClickMap 資料是否已收集。

若 *`trackInlineStats`* 為「true」，則會將點按之頁面與連結的相關資料儲存在名為 s_sq 的 Cookie 中。若為「false」，則 s_sq 的值將為「[[B]]」，將此值視為 Null。

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
