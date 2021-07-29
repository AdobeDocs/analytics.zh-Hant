---
title: 促銷活動
description: 填入「追蹤代碼」維度。
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 89%

---

# 促銷活動

`campaign` 變數專用於收集網站上的追蹤代碼。在舊版 Adobe Analytics 中，它有特殊處理方式，可用來劃分大部分維度。在目前版本的 Adobe Analytics 中，其作用與 eVar 相同。

此變數會填入「追蹤代碼」維度。

## 在Adobe Experience Platform中使用標籤的促銷活動

您可以在設定 Analytics 擴充功能 (全域變數) 時設定促銷活動，或依據規則進行設定。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「促銷活動」]區段。

您可以將促銷活動設為值或查詢字串參數。

## AppMeasurement 和 自訂程式碼編輯器中的 s.campaign

`s.campaign` 變數是字串，通常包含行銷工作中使用的追蹤代碼。最大長度為 255 個位元組；超過 255 個位元組的值會在傳送至 Adobe 時自動截斷。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
