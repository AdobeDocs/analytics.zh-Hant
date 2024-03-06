---
title: 使用 Adobe Experience Platform Edge 實作 Adobe Analytics
description: 在 Adobe Analytics 中使用 Experience Platform 的 XDM 資料 - 總覽
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9d9212313f54e4b44c5341754942ac0e0c78b84c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 95%

---

# 使用 Adobe Experience Platform Edge 實作 Adobe Analytics

Adobe Experience Platform Edge 可讓您將預計要送給多個產品的資料傳送到一個集中位置。 Experience Edge 會將適當的資訊轉送給所需的產品。 此概念可讓您整合實作工作，特別是橫跨多個資料解決方案時。

Adobe 提供三個主要方法將資料傳送給 Experience Edge：

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：在 Adobe Experience Platform Data Collection 中，使用 Web SDK 擴充功能傳送資料給 Edge。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：在 Adobe Experience Platform Data Collection 中，使用 Mobile SDK 擴充功能傳送資料給 Edge。
* **[Adobe Experience Platform Edge Network Server API](server-api/overview.md)**：使用 API 將資料直接傳送給 Edge。



## Adobe Analytics 如何處理 Experience Edge 資料

傳送到 Experience Edge 的資料必須符合以[ XDM (體驗資料模式)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) 為主的架構。XDM 讓您在定義哪些欄位為事件一部分時更具靈活性。當事件到達 Adob&#x200B;&#x200B;e Analytics 時，這些事件會轉換為 Adob&#x200B;&#x200B;e Analytics 可以處理的更結構化資料：頁面檢視或連結事件。

XDM 本身並未規定如何定義頁面檢視或連結事件，也未指示 Adob&#x200B;&#x200B;e Analytics 如何處理其承載。例如，與頁面檢視或連結事件 (例如 `eventType`、`web.webPageDetails.pageViews` 或 `web.webInteraction.linkEvents`) 相關的部份現成可用 XDM 欄位完全與實施無關且與 Adob&#x200B;&#x200B;e Analytics 無關。

為了正確處理頁面檢視和連結事件，以下邏輯會套用於傳送至 Adob&#x200B;&#x200B;e Experience Edge 網路並轉送至 Adob&#x200B;&#x200B;e Analytics 的資料。

| XDM 承載包含... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` 或 `web.webPageDetails.URL` 且無 `web.webInteraction.type` | 考慮承載一個&#x200B;**頁面檢視** |
| `web.webInteraction.type` 和 (`web.webInteraction.name` 或 `web.webInteraction.url`) | 考慮承載一個&#x200B;**連結事件** |
| `web.webInteraction.type` 和 (`web.webPageDetails.name` 或 `web.webPageDetails.url`) | 考慮承載一個&#x200B;**連結事件** <br/>`web.webPageDetails.name`和 `web.webPageDetails.URL` 被設定為 `null` |
| 無 `web.webInteraction.type` 和 (無 `webPageDetails.name` 和無 `web.webPageDetails.URL`) | 放棄負載並忽略資料 |

{style="table-layout:auto"}

請參閱 [Adobe Analytics ExperienceEvent完整擴充功能結構欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) 以取得詳細資訊。
