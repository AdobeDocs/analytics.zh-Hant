---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountSelection

 變數可讓您根據各頁面的 URL 動態選取報表套裝。

> [!NOTE]`dynamicAccountSelection` 無法與自訂連結追蹤搭配使用。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | False |

> [!NOTE]如果 `dynamicAccountList` 變數未宣告或設為「false」，則會同時忽略 `dynamicAccountMatch` 和 `dynamicAccountSelection`。

## 語法和可能的值

```js
s.dynamicAccountSelection=[true|false]
```

只有「true」和「false」可做為 *`dynamicAccountSelection`* 的值。

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

* [適用於 JavaScript 的 AppMeasurement](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)不支援動態帳戶選項。

* 請一律使用 [!DNL DigitalPulse Debugger]，確認是哪個報表套裝在接收來自各頁面的資料。
