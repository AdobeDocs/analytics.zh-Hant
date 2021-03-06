---
title: trackingServerSecure
description: 決定在 HTTPS 頁面上傳送影像要求的位置。
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 61%

---

# 跟蹤伺服器安全

Adobe 會接收訪客產生的影像要求，藉此收集您網站上的資料。`trackingServerSecure` 變數能決定透過 HTTPS 傳送影像要求的位置。它也能決定訪客 Cookie 的儲存位置。如果此變數未正確定義，您的實作可能會遭遇資料遺失。

>[!WARNING]
>
>變更此值會導致 AppMeasurement 在不同位置尋找 Cookie。由於訪客 Cookie 會設定在新的位置，報告中的不重複訪客計數可能會暫時激增。

## 使用Web SDK擴展的邊緣域

Web SDK使用 [!UICONTROL 邊緣域] 處理跟蹤伺服器和安全跟蹤伺服器。 可以設定 [!UICONTROL 邊緣域] 配置Web SDK擴展時的值。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
1. 按一下所需的標記屬性。
1. 轉到 [!UICONTROL 擴展] ，然後按一下 **[!UICONTROL 配置]** 按鈕 [!UICONTROL Adobe Experience PlatformWeb SDK]。
1. 設定所需 **[!UICONTROL 邊緣域]** 的子菜單。

請參閱 [配置Adobe Experience PlatformWeb SDK擴展](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) 的子菜單。

>[!TIP]
>
>如果您的組織從AppMeasurement或Analytics擴展實現移到Web SDK，則此欄位可以使用中包含的相同值 `trackingServerSecure` 或 `trackingServer`)。

## 邊緣域手動實現Web SDK

使用 [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant)。 該欄位是確定要向其發送資料的域的字串。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## 使用Adobe Analytics擴展的SSL跟蹤伺服器

「[!UICONTROL SSL 追蹤伺服器]」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 一般]」摺疊式功能表下方的欄位。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「一般」]摺疊式功能表，如此可顯示[!UICONTROL 「SSL 追蹤伺服器」]欄位。

如果此欄位留空，其預設值為 [`trackingServer`](trackingserver.md) 變數中的值。

## AppMeasurement中的s.trackingServerSecure和Analytics擴展自定義代碼編輯器

`s.trackingServerSecure` 變數是包含影像要求傳送位置的字串。它幾乎永遠是您網站的子網域。瀏覽器中的現代化隱私實務通常會使協力廠商 Cookie 變得不可靠。如果此變數留空，其會使用 `s.trackingServer` 變數中的值。

此變數的值幾乎永遠是第一方網域，例如 `data.example.com`。如需第一方 Cookie 處理的詳細資訊，請參閱「核心服務」使用指南中的 [Experience Cloud 中的第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html)。

最初設定第一方 Cookie 實作的個人，也會定義使用的網域和子網域。例如：

```js
s.trackingServerSecure = "data.example.com";
```

CNAME 記錄通常會指向 `data.adobedc.net`、`sc.adobedc.net` 或 `2o7.net` 上的子網域。
