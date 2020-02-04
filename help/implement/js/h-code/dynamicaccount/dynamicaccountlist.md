---
title: dynamicAccountList
description: 建立實作如何決定其報表套裝的邏輯。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# s.dynamicAccountList

> [!IMPORTANT] 動態帳戶僅支援使用舊版JavaScript實施（H代碼）。 目前的AppMeasurement程式庫或Adobe Experience Platform Launch不支援這些變數。

變 `s.dynamicAccountList` 數會動態決定值 `s_account`。 如 `dynamicAccountSelection` 果設為 `true`，則 `dynamicAccountMatch` 會比較變數 `dynamicAccountList`。 如果找到相符項目，則會使用相符的報表套裝ID。

## 語法

此變數是JavaScript檔案自動剖析的字串。

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

有效輸入是以分號分隔的rsid和值配對清單。 每個清單都包含下列項目:

* 一或多個報表套裝 ID (以逗號分隔)
* 一個等號
* 要比對的一或多個字串（以逗號分隔）

字串中只應使用標準ASCII字元。 不要包含空格。

## 範例

在下列所有範例中，頁面 URL 為 `https://example.com/path2/?prod_id=12345`，`dynamicAccountSelection` 變數設為 `true`，`s_account` 變數則設為 `examplersid`。

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## 缺陷、問題和提示

* 此變數中所列的規則會以由左至右的順序套用。若 `dynamicAccountMatch` 變數符合多個規則，系統會使用最左側的規則來決定報表套裝。因此，請將較通用的規則移至清單的右側。
* 若沒有相符的規則，系統則會使用 `s_account` 中的預設報表套裝。
* 若您的頁面儲存至某人的硬碟，或透過網頁型翻譯引擎進行翻譯 (例如 Google 的翻譯頁面)，動態帳戶選項可能將無法使用。
* `dynamicAccountSelection` 規則只會套用至 `dynamicAccountMatch` 中指定的 URL 的區段。
* 請使用 [!DNL Adobe Experience Cloud Debugger] 來測試目的地報表套裝。
