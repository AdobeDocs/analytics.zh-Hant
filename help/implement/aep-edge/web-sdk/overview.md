---
title: 使用 Adobe Experience Platform Web SDK 實施 Adobe Analytics
description: 使用網頁SDK傳送資料給Adobe Analytics。
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 40%

---

# 使用 Adobe Experience Platform Web SDK 實施 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html?lang=zh-Hant) 傳送資料給 Adobe Analytics。 實作Web SDK有兩個主要方法，且每種方法都有兩種實作型別：

| | **從AppMeasurement移轉** | **清除Web SDK實作** |
| --- | --- | --- |
| **使用標籤** | [從Analytics擴充功能移轉至Web SDK擴充功能](analytics-extension-to-web-sdk.md) | [使用Web SDK擴充功能將資料傳送至Adobe Analytics](web-sdk-tag-extension.md) |
| **使用JavaScript** | [從AppMeasurement移轉至Web SDK JavaScript資料庫](appmeasurement-to-web-sdk.md) | [使用網頁Adobe Analytics JavaScript資料庫傳送資料至SDK](web-sdk-javascript-library.md) |

如果您的組織需要新的Web SDK實作，並計畫在未來使用Customer Journey Analytics，Adobe建議使用您自己的結構描述來使用乾淨的Web SDK實作。 請參閱Customer Journey Analytics使用手冊中的[透過Adobe Experience Platform Web SDK擷取資料](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)。

## 其他資源

標記具有可高度客製化的特性。 進一步了解如何在實施中加入適當的資料，以充分運用 Adobe Analytics。

- [標記文件](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant#)：了解此介面的運作方式以及有哪些可用的擴充功能。

- [Adobe Experience Platform Web SDK 文件](https://experienceleague.adobe.com/docs/web-sdk.html?lang=zh-Hant)
