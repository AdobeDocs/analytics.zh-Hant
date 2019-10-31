---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.cookieLifetime

JavaScript 和資料收集伺服器都會使用 變數來決定 Cookie 的有效期限。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | cl | 流量 &gt; 技術 &gt; Cookie (所有訪客相關) 報表 | "" |

If *`cookieLifetime`* is set, it overrides any other cookie expirations for both JavaScript and data collection servers, with one exception, described below. *`cookieLifetime`* 變數可以有下列三個值之一:

* [!DNL Analytics] Cookie
* Cookie
* JavaScript 設定和外掛程式

## 語法和可能的值

```js
s.cookieLifetime="value"
```

可能的值列出如下: 

* ""
* "NONE"
* "SESSION"
* 表示過期前秒數的整數

## 範例

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## 組態設定

無

## 缺陷、問題和提示

*`cookieLifetime`* 會影響 [!DNL Analytics] 追蹤。例如，如果 *`cookieLifetime`* 為兩天，則每月、每季和每年的獨特訪客報表將會不正確。請謹慎設定 *`cookieLifetime`*。
