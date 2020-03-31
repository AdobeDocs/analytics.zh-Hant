---
title: dynamicAccountMatch
description: dynamicAccountMatch 變數決定要在動態帳戶中查看的值。
translation-type: ht
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] 動態帳戶僅支援使用舊版 JavaScript 實施 (H Code)。目前的 AppMeasurement 程式庫或 Adobe Experience Platform Launch 不支援這些變數。

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
* 在透過網頁型翻譯引擎 (例如 Google) 翻譯頁面時，動態帳戶選項無法如預期運作。如需更精確的追蹤，請在伺服器端填入   `s_account` 變數。
