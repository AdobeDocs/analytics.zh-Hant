---
title: 從AppMeasurement移轉至Web SDK
description: 將Adobe Analytics實作從AppMeasurementJavaScript資料庫更新至Web SDK JavaScript資料庫。
exl-id: c90246e8-0f04-4655-9204-33c0ef611b13
source-git-commit: 05690cc8c1ea0364cbab86f35666df1cc1b13e69
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 0%

---

# 從AppMeasurement移轉至Web SDK

此實作路徑涉及有條不紊的移轉方法，以便從AppMeasurement實作移轉到Web SDK JavaScript程式庫實作。 其他實作路徑會在不同頁面上說明：

* [Analytics擴充功能改用Web SDK擴充功能](analytics-extension-to-web-sdk.md)：以順暢而有條不紊的方式，從Adobe Analytics標籤擴充功能移至Web SDK標籤擴充功能。 在您的組織準備好使用Adobe Experience Platform服務(例如Customer Journey Analytics)之前，此方法會抑制使用XDM的需求。 使用`data`物件而非`xdm`物件來傳送資料給Adobe。
* [Web SDK JavaScript程式庫](web-sdk-javascript-library.md)：使用Web SDK JavaScript程式庫(`alloy.js`)的全新Web SDK安裝。 自行管理實作，而不使用標籤UI。 它需要Adobe Analytics ExperienceEvent欄位群組，其中包括要包含在XDM結構描述中的典型Analytics變數。
* [Web SDK標籤擴充功能](web-sdk-tag-extension.md)：全新的Web SDK安裝，您可使用Adobe Experience Platform資料彙集中的標籤來管理實作。 它需要Adobe Analytics ExperienceEvent欄位群組，其中包括要包含在XDM結構描述中的典型Analytics變數。

## 此實作路徑的優缺點

使用此移轉方法的優缺點。 請仔細權衡每個選項，決定哪種方式最適合您的組織。

| 優勢 | 缺點 |
| --- | --- |
| <ul><li>**使用您現有的實作**：雖然此方法需要一些實作變更，但它不需要從頭開始的全新實作。 您可以使用現有的資料層和程式碼，只需對實作邏輯進行最低限度的變更。</li><li>**不需要結構描述**：對於移轉至Web SDK的這個階段，您不需要XDM結構描述。 相反地，您可以填入`data`物件，這會直接將資料傳送到Adobe Analytics。 一旦移轉至Web SDK完成，您就可以為貴組織建立結構描述，並使用資料流對應來填入適用的XDM欄位。 如果移轉流程的這個階段需要結構描述，貴組織將被強制使用Adobe Analytics XDM結構描述。 使用此結構描述會使您的組織未來更難以使用您自己的結構描述。</li></ul> | <ul><li>**實作變更需要開發人員介入**：若要變更Web SDK實作，您必須與開發團隊合作，編輯網站上的程式碼。 [移轉至Web SDK標籤延伸模組](analytics-extension-to-web-sdk.md)的方法可避免此缺點。</li><li>**實作技術債**：由於此方法使用您現有實作的修改形式，因此可能更難追蹤實作邏輯，並在日後需要時執行變更。</li><li>**需要對應才能將資料傳送至Platform**：當您的組織準備使用Customer Journey Analytics時，您必須將資料傳送至Adobe Experience Platform中的資料集。 此動作要求`data`物件中的每個欄位必須是資料流對應工具中的專案，以將其指派給XDM結構描述欄位。 此工作流程只需對應一次，不需要變更實作。 不過，這是在XDM物件中傳送資料時不需要的額外步驟。</li></ul> |

Adobe建議在下列情況下使用此實施路徑：

* 您已有使用Adobe AnalyticsAppMeasurementJavaScript資料庫的實作。 如果您有使用Adobe Analytics標籤擴充功能的實作，請改為遵循[從Adobe Analytics標籤擴充功能移轉至Web SDK標籤擴充功能](analytics-extension-to-web-sdk.md)。
* 您打算在未來使用Customer Journey Analytics，但不想從頭開始使用Web SDK實作來取代您的Analytics實作。 在Web SDK上從頭開始取代實作需要花費最大心力，但同時也提供最可行的長期實作架構。 如果您的組織願意執行乾淨的Web SDK實作，請參閱Customer Journey Analytics使用手冊中的[透過Adobe Experience Platform Web SDK擷取資料](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)。

## 移轉至Web SDK所需的步驟

下列步驟包含需努力達成的具體目標。 按一下每個步驟，以取得如何完成的詳細指示。

+++**1.建立和設定資料流**

在Adobe Experience Platform Data Collection中建立資料流。 當您傳送資料至此資料流時，它會轉送資料至Adobe Analytics。 未來，相同的資料流會將資料轉送給Customer Journey Analytics。

1. 導覽至[experience.adobe.com](https://experience.adobe.com)並使用您的認證登入。
1. 使用右上方的首頁或產品選擇器來導覽至&#x200B;**[!UICONTROL 資料彙集]**。
1. 在左側導覽中，選取&#x200B;**[!UICONTROL 資料串流]**。
1. 選取「**[!UICONTROL 新資料流]**」。
1. 輸入想要的名稱，然後選取&#x200B;**[!UICONTROL 儲存]**。
1. 建立資料流後，請選取&#x200B;**[!UICONTROL 新增服務]**。
1. 在服務下拉式功能表中，選取&#x200B;**[!UICONTROL Adobe Analytics]**。
1. 輸入與您目前傳送分析資料的目標網站相同的報表套裝ID。 按一下「**[!UICONTROL 儲存]**」。

![新增Adobe Analytics服務](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

您的資料流現在已準備好接收資料並傳遞給Adobe Analytics。 請記下資料串流ID，因為此ID在程式碼中設定Web SDK時是必要的。

+++

+++**2. 安裝Web SDK JavaScript程式庫**

參考最新版本的`alloy.js`，以便使用它的方法呼叫。 請參閱[使用JavaScript程式庫安裝Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library)，以取得詳細資訊和要使用的程式碼區塊。

+++

+++**3.設定Web SDK**

使用Web SDK [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview)命令，將您的實作設定為指向上一步驟中建立的資料流。 必須在每個頁面上設定`configure`命令，因此您可以將其與程式庫安裝程式碼一併納入。

在Web SDK `configure`命令中使用[`datastreamId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/datastreamid)和[`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid)屬性：

* 將`datastreamId`設定為在上一步中擷取的資料串流識別碼。
* 將`orgId`設定為您組織的IMS組織。

```js
alloy("configure", {
    datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
    orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

您可以視您組織的實作需求，選擇在[`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview)命令中設定其他屬性。

+++

+++**4.更新程式碼邏輯以使用JSON裝載**

變更您的Analytics實作，使其不依賴`AppMeasurement.js`或`s`物件。 請改為將變數設為格式正確的JavaScript物件，此物件在傳送至Adobe時會轉換為JSON物件。 您的網站上有[資料層](../../prepare/data-layer.md)在設定值時非常有幫助，因為您可以繼續參考這些相同的值。

若要將資料傳送至Adobe Analytics，Web SDK裝載必須將`data.__adobe.analytics`與此物件中設定的所有分析變數搭配使用。 此物件中的變數與其AppMeasurement變數的對應變數具有相同的名稱和格式。 例如，如果您設定`products`變數，請勿像使用XDM一樣將其分割為個別物件。 如果您設定`s.products`變數，請完全將其加入為字串：

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

最終，此承載包含所有需要的值，且實作中`s`物件的所有參考都會被移除。 您可以使用JavaScript提供的任何資源來設定此裝載物件，包括點標籤法來設定個別值。

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {analytics: {}}}};
dataObj.data.__adobe.analytics.pageName = window.document.title;
dataObj.data.__adobe.analytics.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{analytics:{...a}}}};
```

+++

+++**5.更新方法呼叫以使用Web SDK**

更新呼叫[`s.t()`](../../vars/functions/t-method.md)和[`s.tl()`](../../vars/functions/tl-method.md)的所有執行個體，將它們取代為[`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview)命令。 我們需考慮三種情況：

* **頁面檢視追蹤**：以Web SDK `sendEvent`命令取代頁面檢視追蹤呼叫：

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **自動連結追蹤**： [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)設定屬性預設為啟用。 它會自動設定正確的連結追蹤變數，以將資料傳送至Adobe Analytics。 如果您想要停用自動連結追蹤，請在[`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview)命令內將此屬性設定為`false`。

* **手動連結追蹤**： Web SDK在pageview與非頁面檢視呼叫之間沒有個別的命令。 在裝載物件內提供該區別。

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.analytics.linkName = "Example custom link";
  dataObj.data.__adobe.analytics.linkType = "o";
  dataObj.data.__adobe.analytics.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6.驗證並發佈變更**

移除AppMeasurement和`s`物件的所有參考後，請將變更發佈至開發環境，以驗證新實作是否有效。 一旦您驗證一切都正常運作，您就可以將更新發佈到生產環境。

若已正確移轉，您的網站上就不再需要`AppMeasurement.js`，而且可移除此指令碼的所有參考。

+++

此時，您的Analytics實作已完全放在Web SDK上，並已為未來移至Customer Journey Analytics做好充分準備。
