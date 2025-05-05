---
title: trackingServerSecure
description: 決定在 HTTPS 頁面上傳送影像要求的位置。
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 66%

---

# trackingServerSecure

Adobe 會接收訪客產生的影像要求，藉此收集您網站上的資料。`trackingServerSecure` 變數能決定透過 HTTPS 傳送影像要求的位置。它也能決定訪客 Cookie 的儲存位置。如果此變數未正確定義，您的實作可能會遭遇資料遺失。

>[!WARNING]
>
>變更此值會導致 AppMeasurement 在不同位置尋找 Cookie。由於訪客 Cookie 會設定在新的位置，報告中的不重複訪客計數可能會暫時激增。

## 使用Web SDK擴充功能的Edge網域

Web SDK使用[!UICONTROL Edge網域]來處理追蹤伺服器和安全追蹤伺服器。 設定Web SDK擴充功能時，您可以設定所要的[!UICONTROL Edge網域]值。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 移至[!UICONTROL 擴充功能]標籤，然後按一下[!UICONTROL Adobe Experience Platform Web SDK]底下的&#x200B;**[!UICONTROL 設定]**&#x200B;按鈕。
1. 設定所需的&#x200B;**[!UICONTROL Edge網域]**&#x200B;文字欄位。

如需詳細資訊，請參閱Web SDK檔案中的[設定Adobe Experience Platform Web SDK擴充功能](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=zh-Hant)。

>[!TIP]
>
>如果您的組織從AppMeasurement或Analytics擴充功能實作移至Web SDK，此欄位可使用`trackingServerSecure` （或`trackingServer`）中包含的相同值。

## Edge網域手動實作Web SDK

使用[`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant)設定SDK。 欄位是字串，可決定要將資料傳送至哪個網域。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## 使用Adobe Analytics擴充功能的SSL追蹤伺服器

「[!UICONTROL SSL 追蹤伺服器]」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 一般]」摺疊式功能表下方的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「一般」]摺疊式功能表，如此可顯示[!UICONTROL 「SSL 追蹤伺服器」]欄位。

如果此欄位留空，其預設值為 [`trackingServer`](trackingserver.md) 變數中的值。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.trackingServerSecure

`s.trackingServerSecure` 變數是包含影像要求傳送位置的字串。它幾乎永遠是您網站的子網域。瀏覽器中的現代化隱私實務通常會使協力廠商 Cookie 變得不可靠。如果此變數留空，其會使用 `s.trackingServer` 變數中的值。

此變數的值幾乎永遠是第一方網域，例如 `data.example.com`。如需第一方 Cookie 處理的詳細資訊，請參閱「核心服務」使用指南中的 [Experience Cloud 中的第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=zh-Hant)。

最初設定第一方 Cookie 實作的個人，也會定義使用的網域和子網域。例如：

```js
s.trackingServerSecure = "data.example.com";
```

CNAME 記錄通常會指向 `data.adobedc.net`、`sc.adobedc.net` 或 `2o7.net` 上的子網域。
