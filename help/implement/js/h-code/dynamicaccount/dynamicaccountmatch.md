---
title: dynamicAccountMatch
description: dynamicAccountMatch變數會決定在動態帳戶中要查看的值。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] 動態帳戶僅支援使用舊版JavaScript實施（H代碼）。 目前的AppMeasurement程式庫或Adobe Experience Platform Launch不支援這些變數。

變 `dynamicAccountMatch` 數是查看並比 `dynamicAccountList` 較其值的值。 如果 `dynamicAccountSelection` 未設為， `true`則會忽略此變數。

如果未定義此變數，其預設值為 `window.location.host`。

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

* 儲存至硬碟的頁面未定義數 `location` 個變數(例如， `location.host` 空白)。 請確定包 `s_account` 含預設報表套裝。
* 當透過網頁型翻譯引擎（例如Google）翻譯頁面時，動態帳戶選擇無法如設計般運作。 如需更精確的追蹤，請在伺服器端填入  `s_account` 變數。
