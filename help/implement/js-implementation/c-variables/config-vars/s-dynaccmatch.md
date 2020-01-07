---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountMatch

 變數會使用 DOM 物件來擷取套用了 中所有規則的 URL 區段。

此變數只有在 *`dynamicAccountSelection`* 設為「True」時有效。由於預設值為 [!DNL window.location.host]，因此這個變數並非[!UICONTROL 動態帳戶選項]運作所需的必要項目。如需其他資訊，請參閱 [dynamicAccountList](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。

`dynamicAccountList` 中找到的規則會套用到 `dynamicAccountMatch` 的值。如果 `dynamicAccountMatch` 僅包含 [!DNL window.location.host] (預設)，則 `dynamicAccountList` 中的規則僅能套用到頁面的網域。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | window.location.host |

## 語法和可能的值

`dynamicAccountMatch` 變數通常會由負責提供 JavaScript 適用的 AppMeasurement 檔案的 Adobe 顧問填入。但下方所列的值隨時都可套用。

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

* [適用於 JavaScript 的 AppMeasurement](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)不支援動態帳戶選項。

* 當頁面儲存至硬碟時，[!DNL window.location.host] 會是空的，而使這些頁面檢視傳送至預設報表套裝 (在 `s_account` 中)。

* 在透過網頁型翻譯引擎 (例如 Google) 翻譯頁面時，[!UICONTROL 「動態帳戶選項」]無法如預期運作。如需更精確的追蹤，請在伺服器端填入 [!UICONTROL s_account] 變數。
