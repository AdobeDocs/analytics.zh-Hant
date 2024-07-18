---
title: trackingServer
description: 決定影像要求的傳送位置。
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 284f121428ce9d682b42309dd85cfd117285a7e5
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 52%

---

# trackingServer

Adobe 會接收訪客產生的影像要求，藉此收集您網站上的資料。`trackingServer` 變數決定影像要求的傳送位置。如果此變數未正確定義，您的實作可能會遭遇資料遺失。

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

## 使用Adobe Analytics擴充功能的追蹤伺服器

「追蹤伺服器」是在設定 Adobe Analytics 擴充功能時，位在「[!UICONTROL 一般]」摺疊式功能表底下的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開[!UICONTROL 「一般」]摺疊式功能表，如此可顯示[!UICONTROL 「追蹤伺服器」]欄位。

如果此欄位留空，其預設值為 `[rsid].data.adobedc.net`。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.trackingServer

`s.trackingServer` 變數是包含資料傳送位置的字串。

## 決定`trackingServer`值的考量事項

您可以選擇使用Adobe的追蹤伺服器網域（例如`adobedc.net`），或透過特殊程式來設定符合您網站網域（例如`data.mydomain.com`）的追蹤伺服器，也稱為CNAME實作。 根據您實作的其他方面，擁有符合您網站網域的trackingserver可能會有一些優點。 當追蹤伺服器不符合目前頁面的網域時，AppMeasurement設定的Cookie必須設定為第三方。 如果瀏覽器不支援第三方Cookie，這種不相符可能會干擾某些Analytics功能：

- 設定識別碼：如果您正在使用Experience Cloud識別服務，追蹤伺服器不會影響Cookie的設定方式。 不過，如果您正在使用Analytics舊型識別碼（亦即`s_vi` Cookie），且收集伺服器不符合目前的網域，則Cookie必須設定為第三方。 在此情況下，如果瀏覽器封鎖第三方Cookie，則Analytics會設定第一方備援ID (`s_fid`)，而非標準`s_vi` Cookie。
- 連結追蹤無法用於內部連結。
- 內部連結的Activity Map無法運作。
- Cookie檢查。

### 第一方 Cookie

如果您使用第一方 Cookie 實作，貴組織中可能已經有人完成第一方 Cookie 處理。如需第一方 Cookie 處理的詳細資訊，請參閱「核心服務」使用指南中的 [Experience Cloud 中的第一方 Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html)。

最初設定第一方 Cookie 實作的個人，也會定義使用的網域和子網域。例如：

```js
s.trackingServer = "data.example.com";
```

### 協力廠商追蹤伺服器

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
