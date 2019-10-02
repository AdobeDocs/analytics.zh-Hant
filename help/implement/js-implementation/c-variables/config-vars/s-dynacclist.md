---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# s.dynamicAccountList

> [!NOTE] 目前 `s.dynamicAccountList` 的AppMeasurement程式庫不 [支援變數](../../c-appmeasurement-js/appmeasure-mjs.md)。 它僅用於舊版AppMeasurement，例如H代碼。

變數 `s.dynamicAccountList` 可用來協助動態決定要傳送資料至的報表套裝。 它可與和變數一 `dynamicAccountSelection` 起使 `dynamicAccountMatch` 用。 如果將中 `dynamicAccountList` 的規則設 `dynamicAccountSelection` 為，則會套 `true`用這些規則，並套用至中指定之URL區段 `dynamicAccountMatch`。

## 語法和可能的值

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

Valid input is a semicolon-separated list of name=value pairs (rules). 每個清單都包含下列項目：

* 一或多個報表套裝ID（以逗號分隔）
* 等號
* 一或多個URL篩選器（以逗號分隔）

字串中只應使用標準 ASCII 字元 (無空格)。

## 範例

對於下列所有範例，頁面URL `https://example.com/path2/?prod_id=12345`為， `dynamicAccountSelection` 變數設 `true`定為，變 `s_account` 數設定為 `examplersid`。

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

* 此 此變數中列出的規則會以從左至右的順序套用。 If the `dynamicAccountMatch` variable matches more than one rule, the left-most rule is used to determine the report suite. 因此，請在清單的右側放置更多的一般規則。
* If no rules match, the default report suite in `s_account` is used.
* 如果您的頁面已儲存至某人的硬碟，或是透過網路翻譯引擎（例如Google的翻譯頁面）進行翻譯，動態帳戶選擇可能無法運作。
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.
* Use the [!DNL Adobe Experience Cloud Debugger] to test the destination report suite.
