---
title: dynamicAccountMatch
description: dynamicAccountMatch 變數決定要在動態帳戶中查看的值。
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
TQID: https://experienceleague.adobe.com/Ag4YQOjHPMRsktGSbzpErM55lVCydDHXfNiS4HJofIU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 129
ht-degree: 93%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>動態帳戶僅支援使用舊版 JavaScript 實施作業 (H Code)。 目前 AppMeasurement 資料庫或 Adobe Experience Platform 中的標記不支援這些變數。

`dynamicAccountMatch` 變數是 `dynamicAccountList` 查看及比較值的值。 如果 `dynamicAccountSelection` 未設定為 `true`，此變數會遭到忽略。

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

* 儲存至硬碟的頁面有幾個未定義的 `location` 變數 (例如，`location.host` 是空白的)。 請確認 `s_account` 包含預設報表套裝。
* 在透過網頁型翻譯引擎 (例如 Google) 翻譯頁面時，動態帳戶選項無法如預期運作。 如需更精確的追蹤，請在伺服器端填入`s_account`變數。
