---
title: campaign
description: 填入「追蹤代碼」維度。
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# campaign

此變 `campaign` 數專用於收集網站上的追蹤代碼。 在舊版Adobe Analytics中，它有特殊處理方式，可用來劃分大部分維度。 在目前版本的Adobe Analytics中，其作用與eVar相同。

此變數會填入「追蹤代碼」維度。

## Adobe Experience Platform Launch 中的 Campaign

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定促銷活動。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找出「促 [!UICONTROL 銷活動] 」區段。

您可以將促銷活動設為值或查詢字串參數。

## AppMeasurement和Launch自訂代碼編輯器中的s.campaign

變 `s.campaign` 數是字串，通常包含行銷工作中使用的追蹤代碼。 最大長度為255個位元組；超過100位元組的值會在傳送至Adobe時自動截斷。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
