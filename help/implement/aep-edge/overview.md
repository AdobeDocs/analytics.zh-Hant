---
title: 使用 Adobe Experience Platform Edge 實作 Adobe Analytics
description: 在 Adobe Analytics 中使用 Experience Platform 的 XDM 資料 - 總覽
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9d9212313f54e4b44c5341754942ac0e0c78b84c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 35%

---

# 使用 Adobe Experience Platform Edge 實作 Adobe Analytics

Adobe Experience Platform Edge 可讓您將預計要送給多個產品的資料傳送到一個集中位置。 Experience Edge 會將適當的資訊轉送給所需的產品。 此概念可讓您整合實作工作，特別是橫跨多個資料解決方案時。

Adobe 提供三個主要方法將資料傳送給 Experience Edge：

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**：在 Adobe Experience Platform Data Collection 中，使用 Web SDK 擴充功能傳送資料給 Edge。
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**：在 Adobe Experience Platform Data Collection 中，使用 Mobile SDK 擴充功能傳送資料給 Edge。
* **[Adobe Experience Platform Edge Network伺服器API](server-api/overview.md)**：使用API直接傳送資料給Edge。



## Adobe Analytics如何處理Experience Edge資料

傳送至Experience Edge的資料必須符合以下基準的結構描述： [XDM （體驗資料模型）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant). XDM可讓您靈活選擇將哪些欄位定義為事件的一部分。 當事件到達Adobe Analytics時，這些事件會轉換為Adobe Analytics可處理的更多結構化資料：頁面檢視或連結事件。

XDM本身不會規定如何定義頁面檢視或連結事件，也不會指示Adobe Analytics如何處理其裝載。 例如，某些立即可用的XDM欄位似乎與頁面檢視或連結事件有關，例如 `eventType`， `web.webPageDetails.pageViews`，或 `web.webInteraction.linkEvents` 與實作完全無關，且與Adobe Analytics無關。

為了正確處理頁面檢視和連結事件，下列邏輯會套用至傳送至AdobeExperience Edge網路並轉送至Adobe Analytics的資料。

| XDM承載包含…… | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` 或 `web.webPageDetails.URL` 而否 `web.webInteraction.type` | 將裝載視為 **頁面檢視** |
| `web.webInteraction.type` 和(`web.webInteraction.name` 或 `web.webInteraction.url`) | 將裝載視為 **連結事件** |
| `web.webInteraction.type` 和(`web.webPageDetails.name` 或 `web.webPageDetails.url`) | 將裝載視為 **連結事件** <br/>`web.webPageDetails.name` 和 `web.webPageDetails.URL` 設為 `null` |
| 否 `web.webInteraction.type` 和(否 `webPageDetails.name` 而否 `web.webPageDetails.URL`) | 捨棄裝載並忽略資料 |

{style="table-layout:auto"}

請參閱 [Adobe Analytics ExperienceEvent完整擴充功能結構欄位群組](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) 以取得詳細資訊。
