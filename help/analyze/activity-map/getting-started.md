---
title: Activity Map 快速入門
description: 使用 Activity Map 疊加層與維度快速入門。
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: a7670fcda3e8e6af0c036c8b263746e142278255
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 100%

---

# Activity Map 快速入門

Adobe Analytics 中的 Activity Map 由四個主要元素組成：

* **報告套裝設定**：您必須在報告套裝設定中啟用 Activity Map。啟用後，報告套裝會為 Activity Map 維度和量度建立數個保留變數。
* **實施**：收集您的網站或資產上的 Activity Map 資料。自訂資料彙集方式可提升報告的品質與體驗。
* **Workspace 維度與量度**：當您的實施內容設定正確時，就可以在 Analysis Workspace 中使用 Activity Map 維度與量度。
* **疊加層**：Adobe 提供瀏覽器擴充功能，讓您在網站環境中檢視 Activity Map 資料。此功能不適用於 Web SDK 實施方式。

## 啟用報告套裝設定

報告套裝必須先啟用 Activity Map 報告功能，然後才能開始收集資料。如果您的實施將 Activity Map 資料傳送至未啟用 Activity Map 報告功能的報告套裝，該點擊中不會包含 Activity Map 資料。

**[!UICONTROL 「管理」]**>**[!UICONTROL 「報告套裝」]**>「選取報告套裝」>**[!UICONTROL 「編輯設定」]**>**[!UICONTROL 「Activity Map」]**>**[!UICONTROL 「Activity Map 報告」]**>**[!UICONTROL 「啟用 Activity Map 報告」]**

啟用 Activity Map 報告會建立數個後端保留變數。如需更多資訊，請參閱 Adobe Analytics 管理指南中的[ Activity Map 報告](/help/admin/tools/manage-rs/edit-settings/activity-map.md)。

## 程式碼安裝

您的實施必須正確設定，才能將 Activity Map 資料傳送至 Adobe。使用 Web SDK 方式實施 Adobe Analytics 時，疊加層瀏覽器擴充功能將無法使用。

+++Web SDK 標記擴充功能

Activity Map 資料彙集需要 **[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;擴充功能 v2.23 或以上。低至 v2.16 的擴充功能版本僅提供有限支援。這些先前的擴充功能版本會以獨立事件的方式來傳送 Activity Map 資料，與您其餘的資料分開。此一額外事件會增加您傳送至 Adobe Analytics 或 Adobe Experience Platform 的點擊數。

**[!UICONTROL 點按資料彙集]**&#x200B;設定負責收集 Activity Map 資料，且通常會預設啟用。您可以在擴充功能的設定中檢查，確認該功能已啟用：

1. 登入 [experience.adobe.com](https://experience.adobe.com)
1. 在快速存取功能表或右上角的產品選擇器中，選取&#x200B;**[!UICONTROL 「資料彙集」]**。
1. 在左側導覽功能表中，選取&#x200B;**[!UICONTROL 「標記」]**。
1. 選取要編輯的標記。
1. 在左側導覽功能表中，選取&#x200B;**[!UICONTROL 「擴充功能」]**。
1. 在已安裝的擴充功能清單中，選取&#x200B;**[!UICONTROL 「Adobe Experience Platform Web SDK」]**，然後在右側選取&#x200B;**[!UICONTROL 「設定」]**。
1. 找到標示為[!UICONTROL 「資料彙集」]的區段，並確認已啟用&#x200B;**[!UICONTROL 「啟用點按資料彙集」]**&#x200B;核取方塊。
1. 選取&#x200B;**[!UICONTROL 「儲存」]**。
1. 如有需要，請將您的變更建置到程式庫中，並將變更發佈至生產環境。

如需更多資訊，請參閱[設定 Web SDK 標記擴充功能](https://experienceleague.adobe.com/tw/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection)。

+++

+++Web SDK JavaScript 程式庫 (`alloy.js`)

收集 Activity Map 資料需使用 Web SDK JavaScript 程式庫 v2.20 或以上版本。低至 v2.15 的程式庫版本僅提供有限支援。這些先前的程式庫版本會以獨立事件的方式來傳送 Activity Map 資料，與您其餘的資料分開。此一額外事件會增加您傳送至 Adobe Analytics 或 Adobe Experience Platform 的點擊數。

Web SDK 設定變數 [`clickCollectionEnabled`](https://experienceleague.adobe.com/tw/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) 會負責自動收集 Activity Map 資料。除非明確停用，否則會預設啟用。

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Adobe Analytics 標記擴充功能

**[!UICONTROL 使用 Activity Map]** 設定會負責收集 Activity Map 資料，且通常是預設啟用。所有 v1.9.0 或以上版本的標記擴充功能皆可使用此設定。您可以在擴充功能的設定中檢查，確認該功能已啟用：

1. 登入 [experience.adobe.com](https://experience.adobe.com)
1. 在快速存取功能表或右上角的產品選擇器中，選取&#x200B;**[!UICONTROL 「資料彙集」]**。
1. 在左側導覽功能表中，選取&#x200B;**[!UICONTROL 「標記」]**。
1. 選取要編輯的標記。
1. 在左側導覽功能表中，選取&#x200B;**[!UICONTROL 「擴充功能」]**。
1. 在已安裝的擴充功能清單中選取&#x200B;**[!UICONTROL 「Adobe Analytics」]**，然後在右側選取&#x200B;**[!UICONTROL 「設定」]**。
1. 請確認已啟用&#x200B;**[!UICONTROL 「使用 Activity Map」]**&#x200B;核取方塊。
1. 選取&#x200B;**[!UICONTROL 「儲存」]**。
1. 如有需要，請將您的變更建置到程式庫中，並將變更發佈至生產環境。

如需更多資訊，請參閱 [Adobe Analytics 擴充功能概觀](https://experienceleague.adobe.com/tw/en/docs/experience-platform/tags/extensions/client/analytics/overview)。

+++

+++Adobe Analytics JavaScript 資料庫 (`AppMeasurement.js`)

Activity Map 模組負責收集 Activity Map 資料，而且所有 v1.6 或以上的 AppMeasurement 程式庫皆包含此模組。您可以檢查 `AppMeasurement.js` 檔案，以確認其中包含此模組。

1. 導覽至 GitHub 上[最新的 Adobe Analytics AppMeasurement 版本](https://github.com/adobe/appmeasurement/releases/latest)。
1. 下載壓縮的 AppMeasurement 程式庫檔案，然後開啟其中包含的 `AppMeasurement.js`。
1. Activity Map 模組包含在此檔案靠近頂部的位置。請確保您的網站所使用的 AppMeasurement 程式庫中包含此模組。

+++

## 可用維度

當報告套裝與實施皆已啟用 Activity Map 時，您就可以在 Analysis Workspace 中開始使用下列維度：

* [[!UICONTROL Activity Map 連結]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Activity Map 區域]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Activity Map 頁面]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL 依區域區分的 Activity Map 連結]](/help/components/dimensions/activity-map-link-by-region.md)

## 下載並安裝瀏覽器擴充功能或附加元件

除了在 Analysis Workspace 中可用的維度之外，您也可以在網站上以疊加層的方式檢視 Activity Map 資料。若要檢視此疊加層，請下載並安裝 Activity Map 瀏覽器擴充功能或附加元件。

**[!UICONTROL 「工具」]**>**[!UICONTROL 「Activity Map」]**>**[!UICONTROL 「下載 Activity Map」]**

此連結會帶您前往瀏覽器所支援的擴充功能或附加元件市場，而您可在該處進行安裝。安裝完成後，該擴充功能或附加元件會顯示在瀏覽器右上角，而您可在那裡登入並啟用疊加層。
