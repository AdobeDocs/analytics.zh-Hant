---
title: trackingServerSecure
description: 用來透過HTTPS將資料傳送至Adobe的網域。
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8-M-5apvXuUfQyxdd4Es8Lr5LkgXPK2UNHrhpTzT8xE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 832a3752ab758d573e5b15b2dc38dad120fe8300
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 11%
---
# trackingServerSecure

`trackingServerSecure`變數決定了AppMeasurement用來透過HTTPS將資料傳送至Adobe的網域。 如果此變數未正確定義，您的實施可能會遭遇資料遺失。

>[!NOTE]
>
>[`trackingServer`](configuration-variables.md#retired-configuration-variables)是此變數的淘汰變體。 它指定透過HTTP傳送的資料網域；如果是HTTPS盛行，請改用`trackingServerSecure`。 如果`s.trackingServerSecure`為空白，AppMeasurement會退回至`s.trackingServer`值。

## 使用Web SDK擴充功能的Edge網域

Web SDK使用[!UICONTROL Edge網域]來處理追蹤伺服器和安全追蹤伺服器。 設定Web SDK擴充功能時，您可以設定所需的[!UICONTROL Edge網域]值。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 選取所需的標籤屬性。
1. 移至[!UICONTROL 擴充功能]標籤，然後選取[!UICONTROL Adobe Experience Platform Web SDK]下的&#x200B;**[!UICONTROL 設定]**&#x200B;按鈕。
1. 設定所需的&#x200B;**[!UICONTROL Edge網域]**&#x200B;文字欄位。

如需詳細資訊，請參閱Web SDK檔案中的[設定Adobe Experience Platform Web SDK擴充功能](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=zh-Hant)。

>[!TIP]
>
>如果您的組織從AppMeasurement或Analytics擴充功能實作移至Web SDK，此欄位可使用`trackingServerSecure` （或`trackingServer`）中包含的相同值。

## Edge網域手動實作Web SDK

使用[`edgeDomain`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/commands/configure/edgedomain)設定SDK。 欄位是字串，可決定要將資料傳送至哪個網域。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## 使用Adobe Analytics擴充功能的SSL追蹤伺服器

「[!UICONTROL SSL 追蹤伺服器]」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 一般]」摺疊式功能表下方的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 選取所需的標籤屬性。
1. 移至[!UICONTROL 擴充功能]標籤，然後選取Adobe Analytics底下的&#x200B;**[!UICONTROL 設定]**&#x200B;按鈕。
1. 展開[!UICONTROL 「一般」]摺疊式功能表，如此可顯示[!UICONTROL 「SSL 追蹤伺服器」]欄位。

如果此欄位留空，其預設值為[!UICONTROL 追蹤伺服器]中的值。 如果[!UICONTROL SSL追蹤伺服器]和[!UICONTROL 追蹤伺服器]皆為空白，其預設值為`[rsid].data.adobedc.net`。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.trackingServerSecure

`s.trackingServerSecure`變數是字串，其中包含要傳送資料至Adobe的網域。 這僅是網域；省略通訊協定、路徑、連線埠和斜線。 如果此變數為空白，則會使用`s.trackingServer`變數中的值。 如果`s.trackingServerSecure`和`s.trackingServer`皆為空白，其預設值為`[rsid].2o7.net`。

```js
// Example value when using a first-party domain
s.trackingServerSecure = "data.example.com";

// Example value when using a third-party domain
s.trackingServerSecure = "example.data.adobedc.net";
```

## 決定`trackingServerSecure`值的考量事項

您用於`trackingServerSecure` （或`edgeDomain`）的值取決於您的組織如何將資料傳送至Adobe：

* **如果您的組織使用第一方網域**，例如透過[Adobe管理的憑證方案](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/data-collection/adobe-managed-cert)、[客戶管理的憑證](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/data-collection/customer-managed-cert)或[內容傳遞網路(CDN)](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/data-collection/cdn)，請將該值設定為該網域。 例如，`data.example.com`。
* **如果您的組織使用協力廠商網域**，請將此值設定為`data.adobedc.net`的租使用者ID子網域。 例如，`example.data.adobedc.net`。

請參閱CX Enterprise介面與管理指南中的[選擇資料收集網域](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/data-collection/collection-domain)，以取得每個選項的詳細資訊，包括如何尋找您的租使用者ID。

Adobe強烈建議將此資訊保留在[解決方案設計檔案](../../prepare/solution-design.md)中，以在整個組織內保持一致。

## 不使用訪客ID服務或Experience Platform Identity服務所產生的影響

Adobe強烈建議在所有實作中使用ECID作為訪客身分的主要形式。 您可透過數種不同的方式實作ECID，具體取決於實作型別：

* 手動AppMeasurement實作使用`VisitorAPI.js`並呼叫`getInstance`方法。 如需詳細資訊，請參閱[實作Analytics的訪客ID服務](https://experienceleague.adobe.com/zh-hant/docs/id-service/using/implementation/setup-analytics)。
* 使用Adobe Analytics標籤擴充功能的實作使用[[!UICONTROL Experience Cloud ID服務]標籤擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/id-service/overview)，這會實作訪客ID服務。 新增後，就不需要其他設定。
* 使用任何形式的Web SDK （`alloy.js`或Web SDK標籤擴充功能）的實施會自動包含Experience Platform Identity Service。 設定`edgeDomain`值之後不需要設定。

**如果您的實作不使用ECID**，請考慮下列對實作的影響：

* 如果未使用訪客ID服務或Experience Platform Identity服務，`trackingServerSecure`會決定Cookie位置。 將此變數設為協力廠商網域會強制AppMeasurement使用備援Cookie，因為大部分的現代瀏覽器都會拒絕協力廠商Cookie。
* 內部連結追蹤和Activity Map可能不太可靠。
