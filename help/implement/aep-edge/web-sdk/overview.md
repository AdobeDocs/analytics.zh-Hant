---
title: 使用 Adobe Experience Platform Web SDK 實作 Adobe Analytics
description: 在 Adobe Experience Platform 資料彙集中使用 Web SDK 擴充功能傳送資料給 Adobe Analytics。
source-git-commit: e6b40881a543b43c03b612c7e7b0d9bd09f44c0d
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 23%

---

# 使用 Adobe Experience Platform Web SDK 實作 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html) 傳送資料給 Adobe Analytics。 此實作方法的運作方式是將[體驗資料模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) 轉譯成 Analytics 所使用的格式。

您可以直接使用Web SDK或透過「標籤」中的Web SDK擴充功能，將資料傳送至Experience Edge。

## Web SDK

實作工作的概觀：

![使用Web SDK工作流程實作Adobe Analytics](../../assets/websdk-annotated.png)

|<div style="width:20px"></div>|任務 |更多資訊 | |-| —|—| | 1 |確定您 **定義報表套裝**. | [報表套裝管理器](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **設定結構和資料集**. 為了標準化資料收集，以便在運用Adobe Experience Platform的應用程式間使用，Adobe建立了開放且公開記錄的標準Experience Data Model(XDM)。 | [結構描述UI概述](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant) 和 [資料集UI概觀](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant) | | 3 | **建立資料層** 管理網站上資料的追蹤。 | [建立資料層](../../prepare/data-layer.md) | | 4 | **安裝預先建置的獨立版本**. 您可以參考程式庫(`alloy.js`)，或下載並托管於您自己的基礎架構上。 或者，您也可以使用NPM套件。 | [安裝預先建置的獨立版本](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-2%3A-installing-the-prebuilt-standalone-version) 和 [使用NPM套件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=en#option-3%3A-using-the-npm-package)| | 5 | **設定資料流**. 資料流代表實作Adobe Experience Platform Web SDK時的伺服器端設定。 | [設定資料流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 6 | **新增Adobe Analytics服務** 資料流。 該服務會控制資料是否以及如何傳送至Adobe Analytics。 | [將Adobe Analytics服務新增至資料流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 7 | **配置Web SDK**. 請確定您在步驟4安裝的程式庫已正確設定資料流ID（先前稱為邊緣設定ID）(`edgeConfigId`)，組織id(`orgId`)和其他可用選項。 | [配置Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) | | 8 | **執行命令** 和/或 **追蹤事件**. 在您的網頁上實作基礎程式碼後，您就可以開始使用SDK執行命令及追蹤事件。 | [執行命令](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/executing-commands.html?lang=en) 和 [追蹤事件](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=en) | | 9 | **擴充及驗證實作** 再推出生產。 | |



## Web SDK擴充功能

實作工作的概觀：

![使用Web SDK擴充功能工作流程實作Adobe Analytics](../../assets/websdk-extension-annotated.png)

|<div style="width:20px"></div> |任務 |更多資訊 | |-| —|—| | 1 |確定您 **定義報表套裝**. | [報表套裝管理器](../../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **設定結構和資料集**. 為了標準化資料收集，以便在運用Adobe Experience Platform的應用程式間使用，Adobe建立了開放且公開記錄的標準Experience Data Model(XDM)。 | [結構描述UI概述](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=zh-Hant) 和 [資料集UI概觀](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html?lang=zh-Hant) | | 3 | **建立資料層** 管理網站上資料的追蹤。 | [建立資料層](../../prepare/data-layer.md) | | 4 | **設定資料流**. 資料流代表實作Adobe Experience Platform Web SDK時的伺服器端設定。 | [設定資料流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en) | | 5 | **新增Adobe Analytics服務** 資料流。 該服務會控制資料是否以及如何傳送至Adobe Analytics。 | [將Adobe Analytics服務新增至資料流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#analytics) | | 6 | **建立標籤屬性**. 屬性是用於參考標籤管理資料的整體容器。| [建立或設定Web的標籤屬性](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=en#for-web) | | 7 | **安裝及設定Web SDK擴充功能** 在標籤屬性中。 設定Web SDK擴充功能，將資料傳送至步驟4中設定的資料流。 | [Adobe Experience Platform Web SDK擴充功能概述](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=en) | | 8 | **迭代、驗證和發佈** 生產。 將標籤屬性新增至您的網站。 然後使用資料元素、規則等來自訂您的實作。 | [發佈概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en) |



## 其他資源

標記具有可高度客製化的特性。 進一步了解如何在實作中加入適當的資料，以充分運用 Adobe Analytics。

- [標記文件](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#)：了解此介面的運作方式以及有哪些可用的擴充功能。

- [Adobe Experience Platform Web SDK檔案](https://experienceleague.adobe.com/docs/web-sdk.html?lang=zh-Hant)
