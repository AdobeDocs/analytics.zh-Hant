---
title: trackingServerSecure
description: 用來透過HTTPS將資料傳送至Adobe的網域。
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7918b18e73618368543a996ca121b64b7afb33ab
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 13%

---

# trackingServerSecure

`trackingServerSecure`變數決定了AppMeasurement用來透過HTTPS將資料傳送至Adobe的網域。 如果此變數未正確定義，您的實作可能會遭遇資料遺失。

在[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/zh-hant/docs/id-service/using/home)之前，此變數也會決定協力廠商Cookie的設定位置。 Adobe強烈建議儘可能在所有實施中使用ID服務。

## 使用Web SDK擴充功能的Edge網域

Web SDK使用[!UICONTROL Edge網域]來處理追蹤伺服器和安全追蹤伺服器。 設定Web SDK擴充功能時，您可以設定所需的[!UICONTROL Edge網域]值。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 選取所需的標籤屬性。
1. 移至[!UICONTROL 擴充功能]標籤，然後選取&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;下的[!UICONTROL 設定]按鈕。
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
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## 決定`trackingServerSecure`值的考量事項

您用於`trackingServerSecure` （或`edgeDomain`）的值取決於幾個因素：

* 您參與[Adobe管理的憑證方案](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/data-collection/adobe-managed-cert)
* 若您已實作並正確設定[Adobe Experience Cloud Identity服務](https://experienceleague.adobe.com/zh-hant/docs/id-service/using/home)

**如果您的組織參與Adobe管理的憑證方案**，請將值設定為設定憑證時選取的第一方網域。 通常此值是您的組織所擁有的子網域。 例如，`data.example.com`。貴組織中的CNAME記錄會將該資料重新導向至Adobe。

**如果未參與憑證方案**，請將值設定為`data.adobedc.net`的子網域。 Adobe建議您使用組織的公司ID來維持一致性。 例如，`example.data.adobedc.net`。使用下列步驟來決定您的公司ID：

1. 使用您的Adobe ID憑證登入[experience.adobe.com](https://experience.adobe.com)。
1. 在Experience Cloud介面中的任何位置，按下`[Cmd]` + `[I]` (iOS)或`[Ctrl]` + `[I]` (Windows)。
1. 出現&#x200B;**[!UICONTROL 使用者資料偵錯工具]**。 選取&#x200B;**[!UICONTROL 指派的組織]**&#x200B;索引標籤。
1. 展開所需的IMS組織。
1. 找到&#x200B;**[!UICONTROL 租使用者]**&#x200B;欄位。 建議使用此值的`data.adobedc.net`子網域。

>[!NOTE]
>
>請勿使用比 `example.data.adobedc.net` 更深入的子網域。例如，`custom.example.data.adobedc.net` 不是有效的追蹤伺服器。

舊版實作可能有`sc.omtrdc.net`或`2o7.net`之類的值。 這些主要用於舊版 Adobe Analytics，而且仍然有效。

Adobe強烈建議將此資訊保留在[解決方案設計檔案](../../prepare/solution-design.md)中，以在整個組織內保持一致。

## 不使用訪客ID服務所產生的影響

Adobe強烈建議在所有實作中使用[Adobe Experience Cloud Identity服務](https://experienceleague.adobe.com/zh-hant/docs/id-service/using/home)。 ID服務可透過數種不同的方式實作：

* 手動AppMeasurement實作使用`VisitorAPI.js`並呼叫`getInstance`方法。 如需詳細資訊，請參閱[實作適用於Analytics的Experience Cloud Identity服務](https://experienceleague.adobe.com/zh-hant/docs/id-service/using/implementation/setup-analytics)。
* 使用Adobe Analytics標籤擴充功能的實作使用[Adobe Experience Cloud ID服務標籤擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/id-service/overview)。 新增後，就不需要其他設定。
* 使用任何形式的Web SDK (`alloy.js`或Web SDK標籤擴充功能)的實作已原生內建ID服務。 設定`edgeDomain`值之後不需要設定。

**如果您的實作未使用Identity Service**，請考慮下列對實作的影響：

* 如果未使用身分識別服務，`trackingServerSecure`會決定Cookie位置。 將此變數設為協力廠商網域會強制AppMeasurement使用備援Cookie，因為大部分的現代瀏覽器都會拒絕協力廠商Cookie。
* 內部連結追蹤和Activity Map可能不太可靠。
