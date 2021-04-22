---
title: referrer
description: 覆寫點擊的自動收集反向連結。
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '258'
ht-degree: 100%

---

# referrer

`referrer` 變數會覆寫報表中自動收集的反向連結。在反向連結可能遺失的情況下 (如重新導向期間或將訪客暫時轉送至付款處理者)，此變數很有幫助。此變數有助於填入「反向連結」和「反向連結網域」維度。

## Adobe Experience Platform Launch 中的反向連結

您可以在設定 Analytics 擴充功能 (全域變數) 時設定反向連結，或依據規則進行設定。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 將[!UICONTROL 「擴充功能」]下拉式清單設為「Adobe Analytics」，再將[!UICONTROL 「動作類型」]設為[!UICONTROL 「設定變數」]。
6. 找出[!UICONTROL 「反向連結」]區段。

您可以將反向連結設為任何字串值，包括資料元素。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.referrer

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
