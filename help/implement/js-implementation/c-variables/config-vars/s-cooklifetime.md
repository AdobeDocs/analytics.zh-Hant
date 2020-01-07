---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieLifetime

JavaScript 和資料收集伺服器都會使用 變數來決定 Cookie 的有效期限。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | cl | 流量 &gt; 技術 &gt; Cookie (所有訪客相關) 報表 | "" |

如果您設定了 *`cookieLifetime`*，此變數會覆寫 JavaScript 和資料收集伺服器的任何其他 Cookie 有效期，但有一個例外，以下會有說明。*`cookieLifetime`* 變數可以有下列三個值之一:

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
