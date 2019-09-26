---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountMatch

 變數會使用 DOM 物件來擷取套用了 中所有規則的 URL 區段。

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' 由於預設值為 [!DNL window.location.host]，因此這個變數並非[!UICONTROL 動態帳戶選項]運作所需的必要項目。For additional information, see [dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

The rules found in  are applied to the value of . `dynamicAccountList``dynamicAccountMatch`If  only contains  (default), the rules in  apply only to the domain of the page.`dynamicAccountMatch`[!DNL window.location.host]`dynamicAccountList`

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | window.location.host |

## 語法和可能的值

 此`dynamicAccountMatch` 變數通常會由負責提供「JavaScript 適用的 AppMeasurement」檔案的 Adobe 顧問填入。但下方所列的值隨時都可套用。

```js
s.dynamicAccountMatch=[DOM object]
```

| 說明 | 值 |
|---|---|
| 網域 (預設值) | window.location.host |
| 路徑 | window.location.pathname |
| 查詢字串 | (window.location.search?window.location.search:"?") |
| 網域和路徑 | window.location.host+window.location.pathname |
| 路徑和查詢字串 | window.location.pathname+(window.location.search?window.location.search:"?") |
| 完整 URL | window.location.href |

## 範例

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

## 組態設定

無

## 缺陷、問題和提示

* 動態帳戶選擇不受下列項目支援: [JavaScript 適用的 AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* When pages are saved to a hard drive, [!DNL window.location.host] is empty, causing those page views to be sent to the default report suite (in `s_account`).

* 在透過網頁型翻譯引擎 (例如 Google) 翻譯頁面時，[!UICONTROL 「動態帳戶選項」]無法如預期運作。如需更精確的追蹤，請在伺服器端填入 [!UICONTROL s_account] 變數。
