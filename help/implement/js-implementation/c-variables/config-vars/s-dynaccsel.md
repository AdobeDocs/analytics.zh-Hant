---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountSelection

 變數可讓您根據各頁面的 URL 動態選取報表套裝。

>[!NOTE]
>
>`dynamicAccountSelection` 無法與自訂連結追蹤搭配使用。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | False |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

## 語法和可能的值

```js
s.dynamicAccountSelection=[true|false]
```

只有 'true' 和 'false' 可作為 *另存`dynamicAccountSelection`。*

## 範例

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

## 組態設定

無

## 缺陷、問題和提示

* 動態帳戶選擇不受下列項目支援: [JavaScript 適用的 AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Always use the [!DNL DigitalPulse Debugger] to determine which report suite is receiving data from each page.
