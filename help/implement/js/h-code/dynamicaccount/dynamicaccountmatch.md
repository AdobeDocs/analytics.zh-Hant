---
title: dynamicAccountMatch
description: dynamicAccountMatch 變數決定要在動態帳戶中查看的值。
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 93%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
> 動態帳戶僅支援使用舊版 JavaScript 實施作業 (H Code)。目前 AppMeasurement 資料庫或 Adobe Experience Platform 中的標記不支援這些變數。

`dynamicAccountMatch` 變數是 `dynamicAccountList` 查看及比較值的值。如果 `dynamicAccountSelection` 未設定為 `true`，此變數會遭到忽略。

如果此變數未定義，其預設值為 `window.location.host`。

## 語法

```js
s.dynamicAccountMatch=[DOM object]
```

## 範例

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## 其他附註

* 儲存至硬碟的頁面有幾個未定義的 `location` 變數 (例如，`location.host` 是空白的)。請確認 `s_account` 包含預設報表套裝。
* 在透過網頁型翻譯引擎 (例如 Google) 翻譯頁面時，動態帳戶選項無法如預期運作。如需更精確的追蹤，請在伺服器端填入`s_account`變數。
