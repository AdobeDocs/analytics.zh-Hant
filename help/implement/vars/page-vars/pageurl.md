---
title: pageURL
description: 覆寫在網站上自動收集的頁面 URL。
translation-type: ht
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# pageURL

AppMeasurement 會自動收集每次點擊中的頁面 URL。如果您想要覆寫 AppMeasurement 自動收集的頁面 URL，可以使用此變數。在大多數情況下，您不需要設定此變數。

> [!NOTE] 此變數不是 Analysis Workspace 中的可用維度。它僅適用於 Data Warehouse 和資料摘要。如果您想要在 Analysis Workspace 中將頁面 URL 當做維度，請考慮在每次點擊時將 `pageURL` 變數傳入 eVar。

有時 URL 的長度會超過 255 個位元組。AppMeasurement 會針對影像要求中 URL 的前 255 個位元組使用 `g` 查詢字串參數。如果 URL 的長度超過 255 個位元組，其餘的 URL 會儲存在 `-g` 查詢字串參數中。此變數包含 URL 中的通訊協定和查詢字串。

## Adobe Experience Platform Launch 中的頁面 URL

Launch 會自動填入頁面 URL。不過，您可以在設定 Analytics 擴充功能 (全域變數) 時設定頁面 URL 覆寫，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「頁面 URL」]區段。

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
