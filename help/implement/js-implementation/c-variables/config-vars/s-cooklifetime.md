---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieLifetime

JavaScript 和資料收集伺服器都會使用 變數來決定 Cookie 的有效期限。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | cl | 流量 &gt; 技術 &gt; Cookie (所有訪客相關) 報表 | "" |

若設定了 *`cookieLifetime`*，此變數將會覆寫 JavaScript 和資料收集伺服器的任何其他 Cookie 有效期，但有一個例外，以下會有說明。The *`cookieLifetime`* variable can have one of three values:

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

*`cookieLifetime`* 影響追 [!DNL Analytics] 蹤。 If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Use caution when setting *`cookieLifetime`*.
