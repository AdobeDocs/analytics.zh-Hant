---
title: 追蹤不同的實施類型
description: 使用不同的實施類型，順暢地在不同的實施間追蹤訪客。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: 90914569256cf891cb3cf693843e7cf9ede2f4ce
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 14%

---

# 追蹤不同的實施類型

Adobe Analytics實作的核心架構在所有實作類型中都保持一致。 此程式包括定義變數，並將其編譯為傳送至Adobe資料收集伺服器的影像要求。 此概念表示您可以在同一網站的不同頁面上，順暢地在Adobe Experience Platform資料收集中的AppMeasurement、Web SDK及其各自的擴充功能之間切換。

Adobe建議在所有頁面上使用相同的實作類型，以維護網站實作的一致性。 不過，如果您網站的某些部分有不同的需求，您可以使用此頁面來協助確保在不同頁面間會一致地追蹤訪客。

如果您使用多種類型的實作（例如AppMeasurement和硬式編碼影像要求），請確定下列變數已正確設定且彼此相符：

| 變數 | AppMeasurement | Analytics 擴充功能 | Web SDK | 網頁 SDK 擴充功能 | 硬式編碼影像要求 |
| --- | --- | --- | --- | --- | --- |
| 報表套裝 ID | 內的字串引數 [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL 報表套裝] 在 [!UICONTROL 程式庫管理] 區段 [設定擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | 將Adobe Analytics新增為服務，時機 [設定資料流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | 將Adobe Analytics新增為服務，時機 [設定資料流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | URL的一部分 `pathname` （之後） `/b/ss/`) |
| Tracking Server | 此 [`trackingServer`](../vars/config-vars/trackingserver.md) 和 [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) 變數 | [!UICONTROL 追蹤伺服器] 和 [!UICONTROL SSL追蹤伺服器] 在 [!UICONTROL 一般] 區段 [設定擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | 此 `edgeDomain` 屬性時 [設定Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) | 此 [!UICONTROL 邊緣網域] when [設定擴充功能](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) | 此 `hostname` 影像要求URL的 |
| Experience Cloud ID 服務 | 實作 [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=zh-Hant) | 使用 [Adobe Experience Cloud ID服務擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | 使用 [Adobe Experience Cloud ID服務擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | 使用 [Adobe Experience Cloud ID服務擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | 建立 [個別呼叫ID服務伺服器](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) 取得所需的ID |

{style=&quot;table-layout:auto&quot;}

如果這些變數中的任何一個在每個實施類型中不一致，則Adobe會將它們視為個別訪客。 如果您的網站上沒有順暢地追蹤不同實作類型的訪客，最常見的原因是ID服務的設定不正確。 請參閱 [實作方法](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) 如需詳細資訊，請參閱ID服務使用指南。
