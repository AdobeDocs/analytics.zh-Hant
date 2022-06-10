---
title: trackingServer
description: 決定影像要求的傳送位置。
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 69%

---

# 跟蹤伺服器

Adobe 會接收訪客產生的影像要求，藉此收集您網站上的資料。`trackingServer` 變數決定影像要求的傳送位置。如果此變數未正確定義，您的實作可能會遭遇資料遺失。

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

## 使用Adobe Analytics擴展的跟蹤伺服器

「追蹤伺服器」是在設定 Adobe Analytics 擴充功能時，位在「[!UICONTROL 一般]」摺疊式功能表底下的欄位。

1. 登錄到 [Adobe Experience Platform資料收集](https://experience.adobe.com/data-collection) 使用AdobeID憑據。
2. 按一下所需的標記屬性。
3. 前往[!UICONTROL 擴充功能]標記，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「一般」]摺疊式功能表，如此可顯示[!UICONTROL 「追蹤伺服器」]欄位。

如果此欄位留空，其預設值為 `[rsid].data.adobedc.net`。

## AppMeasurement中的s.trackingServer和Analytics擴展自定義代碼編輯器

`s.trackingServer` 變數是包含資料傳送位置的字串。

## 決定 的值`trackingServer`

此變數的值取決於您是使用第一方 Cookie 或協力廠商 Cookie。Adobe 強烈建議您在實作中使用第一方 Cookie。

### 第一方 Cookie

如果您使用第一方 Cookie 實作，貴組織中可能已經有人完成第一方 Cookie 處理。如需第一方 Cookie 處理的詳細資訊，請參閱「核心服務」使用指南中的 [Experience Cloud 中的第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html)。

最初設定第一方 Cookie 實作的個人，也會定義使用的網域和子網域。例如：

```js
s.trackingServer = "data.example.com";
```

### 協力廠商 Cookie

>[!TIP]
>
>近代瀏覽器中逐漸增強的隱私權實務會降低協力廠商 Cookie 的可靠性。Adobe 建議您遵循第一方 Cookie 工作流程。

如果您使用協力廠商 Cookie 實作，`trackingServer` 的值為 `data.adobedc.net` 的子網域。例如：

```js
s.trackingServer = "example.data.adobedc.net";
```

挑選貴組織專屬的子網域，也就是其他使用 Adobe Analytics 之組織不太可能挑選的子網域。建議您的組織指派的訪客命名空間。確定貴組織的所有實作都使用相同的追蹤伺服器。在[解決方案設計文件](../../prepare/solution-design.md)中維護這些資訊會是比較實用的方法。

您的組織可能已在 `sc.omtrdc.net` 或 `2o7.net` 網域中使用協力廠商追蹤伺服器。這些主要用於舊版 Adobe Analytics，而且仍然有效。

>[!NOTE]
>
>請勿使用比 `example.data.adobedc.net` 更深入的子網域。例如，`custom.example.data.adobedc.net` 不是有效的追蹤伺服器。
