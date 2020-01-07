---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountList

> [!NOTE] [目前的 AppMeasurement 程式庫](../../c-appmeasurement-js/appmeasure-mjs.md)不支援 `s.dynamicAccountList` 變數。該變數僅可用於舊版 AppMeasurement，例如 H 程式碼。

變數 `s.dynamicAccountList` 有助於透過動態方式決定要接收資料的報表套裝。此變數可結合 `dynamicAccountSelection` 和 `dynamicAccountMatch` 變數一起使用。若將 `dynamicAccountSelection` 設為 `true`，系統會套用 `dynamicAccountList` 中的規則，而這些規則會套用至 `dynamicAccountMatch` 中指定的 URL 區塊。

## 語法和可能的值

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

有效的輸入值是以分號分隔的「名稱=值」配對 (規則) 清單。每個清單都包含下列項目:

* 一或多個報表套裝 ID (以逗號分隔)
* 一個等號
* 一或多個 URL 篩選器 (以逗號分隔)

字串中只應使用標準 ASCII 字元 (無空格)。

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
