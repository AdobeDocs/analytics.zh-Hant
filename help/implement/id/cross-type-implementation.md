---
title: 追蹤不同的實施類型
description: 使用不同的實施類型，順暢地在不同的實施間追蹤訪客。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 58%

---

# 追蹤不同的實施類型

Adobe Analytics 實施的核心架構在所有實施類型中都是一致的。該流程涉及定義變數，並將其編譯成傳送至 Adobe 資料收集伺服器的影像要求。這個概念代表您可以在 AppMeasurement、Web SDK 及其在 Adobe Experience Platform 資料收集中的各自擴充功能之間，跨同一網站的不同頁面無縫切換。

Adobe 建議在所有頁面上使用相同的實施類型來保持網站實施的一致性。但是，如果您網站的某些部分有不同的要求，您可以使用此頁面來協助確保跨頁面持續追蹤訪客。

如果您使用多種型別的實施(例如AppMeasurement和硬式編碼影像要求)，請確定下列變數已正確設定並彼此相符。

>[!NOTE]
>
>所有實作型別都必須使用相同的訪客身分識別型別（舊有的Analytics ID或訪客ID服務）。 Adobe建議儘可能在所有實施中使用訪客ID服務。

| 變數 | Web SDK 標記擴充功能 | 網頁SDK (Alloy) | Analytics 擴充功能 | AppMeasurement | 硬式編碼影像要求 |
|---|---|---|---|---|---|
| 報表套裝 ID | [設定資料流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure)時，將 Adobe Analytics 新增為服務 | [設定資料流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure)時，將 Adobe Analytics 新增為服務 | [設定擴充功能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview)時，[!UICONTROL 程式庫管理]部分底下的[!UICONTROL 報告套裝] | [`s_gi`](../vars/functions/s-gi.md)中的字串引數 | URL `pathname` 的一部分 (`/b/ss/` 之後) |
| Experience Cloud ID 服務 | [原生包含](web-sdk-extension.md) | [原生包含](alloy.md) | 使用[Experience Cloud ID服務擴充功能](analytics-extension.md) | 實作 [`VisitorAPI.js`](appmeasurement.md) | 對ID服務[進行](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration)個別呼叫以取得所需的ID，並將`mid`納入查詢字串中 |
| Edge網域 | [!UICONTROL 設定擴充功能]時的[Edge網域](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)欄位 | [設定 Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) 時，`edgeDomain` 屬性 | 在[!UICONTROL 設定擴充功能]時，位於[!UICONTROL 一般]區段下的[SSL追蹤伺服器](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) | [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md)變數 | 影像的 `hostname` 請求 URL |

如果這些變數在每種實施型別中不一致，Adobe可能會將其視為個別訪客。 如果訪客未在您網站上跨實施類型進行無縫追蹤，最常見的原因是 ID 服務設定不正確。請確定每個實作型別在您的網站上正確取得相同的Experience Cloud ID (`mid`)。
