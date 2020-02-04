---
title: pageURL
description: 覆寫網站上自動收集的頁面URL。
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# pageURL

AppMeasurement會自動收集每次點擊中的頁面URL。 如果您想要覆寫AppMeasurement自動收集的頁面URL，可以使用此變數。 在大多數情況下，您不需要設定此變數。

> [!NOTE] 此變數不是分析工作區中的可用維度。 它僅適用於資料倉庫和資料饋送。 如果您想要在「分析工作區」中將頁面URL當做維度，請考慮在每次點 `pageURL` 擊時將變數傳入eVar。

有時URL超過255個位元組。 AppMeasurement會對影 `g` 像請求中的URL前255個位元組使用查詢字串參數。 如果URL長度超過255個位元組，則其餘的URL會儲存在查詢字串 `-g` 參數中。 此變數中包含URL中的通訊協定和查詢字串。

## Adobe Experience Platform Launch中的頁面URL

Launch會自動填入頁面URL。 不過，您可以在設定Analytics擴充功能（全域變數）時或在規則下設定頁面URL覆寫。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找到「 [!UICONTROL 頁面URL] 」區段。

您可以將頁面URL設為任何字串值。

## AppMeasurement和Launch自訂代碼編輯器中的s.pageURL

變 `s.pageURL` 數是包含頁面URL的字串。 AppMeasurement會自動收集此變數，不過您可以視需要覆寫其值。

```js
s.pageURL = "https://example.com";
```

如果您想要將頁面URL用作報表中的維度，請考慮在實作中使用下列項目：

```js
// Set eVar1 to page URL without protocol or query strings
s.eVar1 = window.location.hostname + window.location.pathname;
```
