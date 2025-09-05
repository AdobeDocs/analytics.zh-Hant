---
title: Activity Map快速入門
description: 開始使用Activity Map覆蓋和維度。
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# Activity Map快速入門

Adobe Analytics中的Activity Map包含四個主要元素：

* **報表套裝設定**：您必須在報表套裝設定中啟用Activity Map。 啟用後，報表套裝會針對Activity Map維度和量度建立數個保留變數。
* **實作**：在您的網站或屬性上收集Activity Map資料。 自訂資料收集方式可改善報表的品質和體驗。
* **Workspace維度和量度**：當您的實作已正確設定時，您可以在Analysis Workspace中使用Activity Map維度和量度。
* **覆蓋**： Adobe提供瀏覽器擴充功能，可在您網站的內容中檢視Activity Map資料。

## 啟用報表套裝設定

報表套裝必須啟用Activity Map報表，您才能開始收集資料。 如果您的實施傳送Activity Map資料至未啟用Activity Map報告的報表套裝，則點選中不會包含Activity Map資料。

**[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** >選取報表套裝> **[!UICONTROL 編輯設定]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map報表]** > **[!UICONTROL 啟用Activity Map報表]**

啟用Activity Map報表會建立多個後端保留變數。 如需詳細資訊，請參閱Activity Map管理指南中的[Adobe Analytics報表](/help/admin/tools/manage-rs/edit-settings/activity-map.md)。

## 程式碼安裝

您的實作必須正確設定，才能將Activity Map資料傳送至Adobe。

+++Web SDK 標記擴充功能

Activity Map資料收集需要&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;擴充功能v2.23或更新版本。 擴充功能版本（最低至v2.16）支援有限。 這些先前的擴充功能版本會以與其他資料分開的事件，傳送Activity Map資料。 這個額外的事件會增加您傳送至Adobe Analytics或Adobe Experience Platform的點選次數。

**[!UICONTROL Click資料彙集]**&#x200B;組態設定會處理Activity Map資料彙集，通常預設為啟用。 您可以確認，這已在擴充功能的組態設定中啟用：

1. 登入[experience.adobe.com](https://experience.adobe.com)
1. 選取[快速存取]功能表中的[資料彙集]**[!UICONTROL 或右上方的產品選取器。]**
1. 在左側導覽功能表中選取&#x200B;**[!UICONTROL 標籤]**。
1. 選取要編輯的標籤。
1. 在左側導覽功能表中選取&#x200B;**[!UICONTROL 擴充功能]**。
1. 在已安裝的擴充功能清單中選取&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**，然後在右側選取&#x200B;**[!UICONTROL 設定]**。
1. 找出標示為[!UICONTROL 資料彙集]的區段，並確定核取方塊&#x200B;**[!UICONTROL 啟用[啟用點選資料彙集]]**。
1. 選取「**[!UICONTROL 儲存]**」。
1. 如有需要，請將變更建置至程式庫，並將變更發佈至生產環境。

如需詳細資訊，請參閱[設定Web SDK標籤擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection)。

+++

+++Web SDK JavaScript資料庫(`alloy.js`)

Activity Map資料收集需要Web SDK JavaScript資料庫v2.20或更新版本。 程式庫版本若降至v2.15，則支援有限。 這些舊版程式庫會以與其他資料分開的事件，傳送Activity Map資料。 這個額外的事件會增加您傳送至Adobe Analytics或Adobe Experience Platform的點選次數。

Web SDK設定變數[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)會處理Activity Map資料的自動收集。 除非明確停用，否則預設為啟用。

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Adobe Analytics標籤擴充功能

**[!UICONTROL 使用Activity Map]**&#x200B;組態設定會處理Activity Map資料收集，通常預設為啟用。 它適用於所有標籤擴充功能v1.9.0或更新版本。 您可以確認，這已在擴充功能的組態設定中啟用：

1. 登入[experience.adobe.com](https://experience.adobe.com)
1. 選取[快速存取]功能表中的[資料彙集]**[!UICONTROL 或右上方的產品選取器。]**
1. 在左側導覽功能表中選取&#x200B;**[!UICONTROL 標籤]**。
1. 選取要編輯的標籤。
1. 在左側導覽功能表中選取&#x200B;**[!UICONTROL 擴充功能]**。
1. 選取已安裝擴充功能清單中的&#x200B;**[!UICONTROL Adobe Analytics]**，然後在右側選取&#x200B;**[!UICONTROL 設定]**。
1. 確定核取方塊&#x200B;**[!UICONTROL 使用Activity Map]**&#x200B;已啟用。
1. 選取「**[!UICONTROL 儲存]**」。
1. 如有需要，請將變更建置至程式庫，並將變更發佈至生產環境。

如需詳細資訊，請參閱[Adobe Analytics擴充功能概觀](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview)。

+++

+++Adobe Analytics JavaScript資料庫(`AppMeasurement.js`)

Activity Map模組會處理Activity Map資料收集，並包含在所有AppMeasurement程式庫1.6版或更新版本中。 您可以檢查`AppMeasurement.js`檔案，以確定已包含該檔案。

1. 導覽至GitHub上的[最新Adobe Analytics AppMeasurement版本](https://github.com/adobe/appmeasurement/releases/latest)。
1. 下載壓縮的AppMeasurement程式庫檔案，然後開啟包含在內的`AppMeasurement.js`。
1. Activity Map模組包含在此檔案頂端附近。 請確定此模組包含在您的網站所使用的AppMeasurement程式庫中。

+++

## 適用的維度

為您的報表套裝和實作同時啟用Activity Map後，您就可以在Analysis Workspace中開始使用下列維度：

* [[!UICONTROL Activity Map連結]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map地區]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Map頁面]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL 各地區的Activity Map連結]](/help/components/dimensions/activity-map-link-by-region.md)

## 下載並安裝瀏覽器擴充功能或附加元件

除了Analysis Workspace中可用的維度之外，您也可以在網站上以覆蓋圖檢視Activity Map資料。 若要檢視此覆蓋圖，請下載並安裝Activity Map瀏覽器擴充功能或附加元件。

**[!UICONTROL 工具]** > **[!UICONTROL Activity Map]** > **[!UICONTROL 下載Activity Map]**

此連結會帶您前往瀏覽器支援的擴充功能或附加元件市集，您可以在其中安裝。 安裝後，擴充功能或附加元件會顯示在瀏覽器的右上方，您可以在此登入並啟用覆蓋。
