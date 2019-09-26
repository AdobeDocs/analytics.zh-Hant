---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

 變數可讓您在部署中為動態填入的變數加上標記。

Cookie、要求標題和影像查詢字串參數皆可動態填入。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | D= | 任何 | D= |

## 語法和可能的值

```js
s.prop1="D=User-Agent”
```

或對動態變數使用自訂標幟

```js
s.dynamicVariablePrefix=".."
```

## 範例

```js
s.prop1="D=User-Agent”
```

或對動態變數使用自訂標幟

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

## 缺陷、問題和提示

* 動態變數可藉由將值複製到其他變數中，而大幅降低 URL 的總長度。

* 動態變數可讓您從無法以其他方式用於資料收集的標題和 Cookie 進行資料收集。
