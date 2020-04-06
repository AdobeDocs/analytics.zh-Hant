---
title: pageURL
description: 覆寫在網站上自動收集的頁面 URL。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# pageURL

AppMeasurement 會自動收集每次點擊中的頁面 URL。如果您想要覆寫 AppMeasurement 自動收集的頁面 URL，可以使用此變數。在大多數情況下，您不需要設定此變數。

>[!NOTE] 此變數不是 Analysis Workspace 中的可用維度。它僅適用於 Data Warehouse 和資料摘要。如果您想要在 Analysis Workspace 中將頁面 URL 當做維度，請考慮在每次點擊時將 `pageURL` 變數傳入 eVar。

有時 URL 的長度會超過 255 個位元組。AppMeasurement 會針對影像要求中 URL 的前 255 個位元組使用 `g` 查詢字串參數。如果 URL 的長度超過 255 個位元組，其餘的 URL 會儲存在 `-g` 查詢字串參數中。此變數包含 URL 中的通訊協定和查詢字串。

## Adobe Experience Platform Launch 中的頁面 URL

Launch 會自動填入頁面 URL。不過，您可以在設定 Analytics 擴充功能 (全域變數) 時設定頁面 URL 覆寫，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL Page URL] section.

您可以將頁面 URL 設為任何字串值。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.pageURL

`s.pageURL` 變數是包含頁面 URL 的字串。AppMeasurement 會自動收集此變數，不過您可以視需要覆寫其值。

```js
s.pageURL = "https://example.com";
```

如果您想要將頁面 URL 當做報表中的維度，請考慮在實施中使用下列項目：

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```
