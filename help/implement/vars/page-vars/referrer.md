---
title: referrer
description: 覆寫點擊的自動收集反向連結。
feature: Variables
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 80%

---

# referrer

`referrer` 變數會覆寫報表中自動收集的反向連結。在反向連結可能遺失的情況下 (如重新導向期間或將訪客暫時轉送至付款處理者)，此變數很有幫助。此變數有助於填入「反向連結」和「反向連結網域」維度。

## 使用Web SDK的反向連結

反向連結會對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.web.webReferrer.URL`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.referrer`

Web SDK會在每個已傳送的事件上自動包含`web.webReferrer.URL` （如果有的話）。

## 使用Adobe Analytics擴充功能的反向連結

您可以在設定 Analytics 擴充功能 (全域變數) 時設定反向連結，或依據規則進行設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定為[!UICONTROL 設定變數]。
6. 找出[!UICONTROL 「反向連結」]區段。

您可以將反向連結設為任何字串值，包括資料元素。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.referrer

`s.referrer` 變數是包含上一頁 URL 的字串。此變數最多可儲存 255 個位元組；長度超過 255 個位元組的值會遭到截斷。AppMeasurement 會自動將此變數設為 `document.referrer`。除非您想要覆寫自動收集的值，否則不需要設定此變數。

```js
s.referrer = "https://example.com";
```

如果使用`digitalData` [資料層](../../prepare/data-layer.md):

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>請避免將此變數設為非 URL 的值。切勿移除 URL 的協議。

## 範例

許多組織都必須著手進行與重新導向相關的實施。如果您的網站容許的話，可以使用 [`Util.getQueryParam()`](../functions/util-getqueryparam.md) 公用程式從 URL 取得反向連結。請務必將查詢字串中包含的所有值編碼為 URL。

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
