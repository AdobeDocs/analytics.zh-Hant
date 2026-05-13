---
title: 使用 Adobe Experience Platform Web SDK 實施 Adobe Analytics
description: 使用網頁SDK傳送資料給Adobe Analytics。
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/4pS-q3F3W7D1ojdMkCzgUyZkO3LDt1DpFfxqcTtZXLQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 42%

---

# 使用 Adobe Experience Platform Web SDK 實施 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/web-sdk/home.html) 傳送資料給 Adobe Analytics。 實作Web SDK有兩個主要方法，且每種方法都有兩種實作型別：

| | **從AppMeasurement移轉** | **清除Web SDK實作** |
| --- | --- | --- |
| **使用標籤** | [從Analytics擴充功能移轉至Web SDK擴充功能](analytics-extension-to-web-sdk.md) | [使用Web SDK擴充功能將資料傳送至Adobe Analytics](web-sdk-tag-extension.md) |
| **使用JavaScript** | [從AppMeasurement移轉至Web SDK JavaScript資料庫](appmeasurement-to-web-sdk.md) | [使用網頁Adobe Analytics JavaScript資料庫傳送資料至SDK](web-sdk-javascript-library.md) |

如果您的組織需要新的Web SDK實作，並計畫在未來使用Customer Journey Analytics，Adobe建議使用您自己的結構描述來使用乾淨的Web SDK實作。 請參閱Customer Journey Analytics使用手冊中的[透過Adobe Experience Platform Web SDK擷取資料](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk)。

## 其他資源

標記具有可高度客製化的特性。 進一步了解如何在實施中加入適當的資料，以充分運用 Adobe Analytics。

- [標記文件](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=zh-Hant#)：了解此介面的運作方式以及有哪些可用的擴充功能。

- [Adobe Experience Platform Web SDK檔案](https://experienceleague.adobe.com/docs/web-sdk.html?lang=zh-Hant)
