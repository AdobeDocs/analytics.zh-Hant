---
title: dynamicAccountList
description: 建立邏輯，讓實施根據此邏輯決定其報表套裝。
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 94%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
> 動態帳戶僅支援使用舊版 JavaScript 實作 (H Code)。目前的AppMeasurement資料庫或Adobe Experience Platform資料彙集中不支援這些變數。

`s.dynamicAccountList` 變數會以動態方式決定 `s_account` 的值。如果 `dynamicAccountSelection` 設為 `true`，則會比較 `dynamicAccountMatch` 變數與 `dynamicAccountList`。如果找到相符項目，則會使用相符的報表套裝 ID。

## 語法

此變數是 JavaScript 檔案自動剖析的字串。

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

有效的輸入項目是以分號分隔的 rsid 和值配對清單。每個清單都包含下列項目：

* 一或多個報表套裝 ID (以逗號分隔)
* 一個等號
* 要比對的一或多個字串 (以逗號分隔)

字串中只應使用標準 ASCII 字元。請勿包含空格。

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
