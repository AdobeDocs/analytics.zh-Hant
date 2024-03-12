---
title: 使用 Adobe Experience Platform Edge 實施 Adobe Analytics
description: 在 Adobe Analytics 中使用 Experience Platform 的 XDM 資料 - 總覽
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 50%

---

# 使用Adobe Experience Platform Edge Network實作Adobe Analytics

Adobe Experience Platform Edge Network可讓您將預計要送給多個產品的資料傳送到一個集中位置。 Edge網路會將適當的資訊轉送給所需的產品。 此概念可讓您整合實施工作，特別是橫跨多個資料解決方案時。

Adobe提供三種主要方法將資料傳送至Edge Network：

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：在 Adobe Experience Platform Data Collection 中，使用 Web SDK 擴充功能傳送資料給 Edge。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：在 Adobe Experience Platform Data Collection 中，使用 Mobile SDK 擴充功能傳送資料給 Edge。
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**：使用 API 將資料直接傳送給 Edge。



## Adobe Analytics如何處理Edge Network資料

傳送至Adobe Experience Platform Edge Network的資料可遵循兩種格式：

* XDM物件：根據以下原則符合結構描述： [XDM （體驗資料模型）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant). XDM 讓您在定義哪些欄位為事件一部分時更具靈活性。事件到達Adobe Analytics時，會轉換為Adobe Analytics可處理的格式。
* 資料物件：使用對應至Adobe Analytics的特定欄位，將資料傳送至Edge Network。 Edge Network會偵測這些欄位是否存在，並將這些欄位轉送至Adobe Analytics，而不需要遵守結構描述。


Edge Network會使用下列邏輯來判斷Adobe Analytics頁面檢視和連結事件

| XDM 承載包含... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` 或 `web.webPageDetails.URL` 且無 `web.webInteraction.type` | 考慮承載一個&#x200B;**頁面檢視** |
| `web.webInteraction.type` 和 (`web.webInteraction.name` 或 `web.webInteraction.url`) | 考慮承載一個&#x200B;**連結事件** |
| `web.webInteraction.type` 和 (`web.webPageDetails.name` 或 `web.webPageDetails.url`) | 考慮承載一個&#x200B;**連結事件** <br/>`web.webPageDetails.name`和 `web.webPageDetails.URL` 被設定為 `null` |
| 無 `web.webInteraction.type` 和 (無 `webPageDetails.name` 和無 `web.webPageDetails.URL`) | 放棄負載並忽略資料 |

{style="table-layout:auto"}

請參閱「[Adobe Analytics ExperienceEvent 完整延伸功能綱要欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html)，了解更多資訊。
