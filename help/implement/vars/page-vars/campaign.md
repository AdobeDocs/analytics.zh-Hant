---
title: campaign
description: 填入「追蹤代碼」維度。
translation-type: tm+mt
source-git-commit: 7220b99268532adb2e425d52744dbc3efb615953

---


# campaign

此變 `campaign` 數專用於收集網站上的追蹤代碼。 在舊版Adobe Analytics中，它有特殊處理方式，可用來劃分大部分維度。 在目前版本的Adobe Analytics中，其作用與eVar相同。

此變數會填入「追蹤代碼」維度。

## Adobe Experience Platform Launch 中的 Campaign

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定促銷活動。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Rules] ，然後按一下所要的規則（或建立規則）。
4. 在下 [!UICONTROL Actions]方，按一下現 [!UICONTROL Adobe Analytics - Set Variables] 有動作或按一下「+」圖示。
5. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 為 [!UICONTROL Set Variables]。
6. Locate the [!UICONTROL Campaign] section.

您可以將促銷活動設為值或查詢字串參數。

## AppMeasurement和Launch自訂代碼編輯器中的s.campaign

變 `s.campaign` 數是字串，通常包含行銷工作中使用的追蹤代碼。 最大長度為255個位元組；超過255個位元組的值會在傳送至Adobe時自動截斷。

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
