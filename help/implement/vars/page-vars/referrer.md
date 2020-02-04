---
title: referrer
description: 覆寫點擊的自動收集反向連結。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# referrer

變數 `referrer` 會覆寫報表中自動收集的反向連結。 此變數在反向連結可能遺失的情況下很有幫助，例如在重新導向期間或將訪客暫時轉送至付款處理者。 此變數可協助填入「反向連結」和「反向連結網域」維度。

## Adobe Experience Platform Launch中的反向連結

您可以在設定Analytics擴充功能（全域變數）時或在規則下設定反向連結。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找到「反向 [!UICONTROL 連結] 」區段。

您可以將反向連結設為任何字串值，包括資料元素。

## AppMeasurement和Launch自訂代碼編輯器中的s.referrer

變 `s.referrer` 數是包含上一頁URL的字串。 此變數最多可儲存255個位元組；大於255個位元組的值會被截斷。 AppMeasurement會自動將此變數設為 `document.referrer`;除非您要覆寫自動收集的值，否則您不需要設定此變數。

```js
s.referrer = "https://example.com";
```

請避免將此變數設為非URL值。

## 範例

許多組織都會處理重新導向相關的實施。 如果您的網站 [`getQueryParam`](../functions/util-getqueryparam.md) 容納反向連結，您可以使用公用程式從URL取得反向連結。 請確定您對查詢字串中包含的任何值進行URL編碼。

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
