---
title: 追蹤不同的實施類型
description: 使用不同的實施類型，順暢地在不同的實施間追蹤訪客。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: 90914569256cf891cb3cf693843e7cf9ede2f4ce
workflow-type: ht
source-wordcount: '442'
ht-degree: 100%

---

# 追蹤不同的實施類型

Adobe Analytics 實施的核心架構在所有實施類型中都是一致的。該流程涉及定義變數，並將其編譯成傳送至 Adobe 資料收集伺服器的影像要求。這個概念代表您可以在 AppMeasurement、Web SDK 及其在 Adobe Experience Platform 資料收集中的各自擴充功能之間，跨同一網站的不同頁面無縫切換。

Adobe 建議在所有頁面上使用相同的實施類型來保持網站實施的一致性。但是，如果您網站的某些部分有不同的要求，您可以使用此頁面來協助確保跨頁面持續追蹤訪客。

若您使用多種類型的實施 (例如 AppMeasurement 與硬式編碼影像要求)，請確定下列變數均已正確設定並彼此相符：

| 變數 | AppMeasurement | Analytics 擴充功能 | Web SDK | 網頁 SDK 擴充功能 | 硬式編碼影像要求 |
| --- | --- | --- | --- | --- | --- |
| 報表套裝 ID | [`s_gi`](../vars/functions/s-gi.md) 內的字串引數 | [設定擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=zh-Hant)時，[!UICONTROL 程式庫管理]部分底下的[!UICONTROL 報告套裝] | [設定資料流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant)時，將 Adobe Analytics 新增為服務 | [設定資料流](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=zh-Hant)時，將 Adobe Analytics 新增為服務 | URL `pathname` 的一部分 (`/b/ss/` 之後) |
| 追蹤伺服器 | [`trackingServer`](../vars/config-vars/trackingserver.md) 和 [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) 變數 | [設定擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=zh-Hant)時，[!UICONTROL 一般]區段底下的[!UICONTROL 追蹤伺服器]和 [!UICONTROL SSL 追蹤伺服器] | [設定 Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) 時，`edgeDomain` 屬性 | [設定擴充功能](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=zh-Hant)時，[!UICONTROL Edge 網域] | 影像的 `hostname` 請求 URL |
| Experience Cloud ID 服務 | 實施 [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=zh-Hant) | 使用 [Adobe Experience Cloud ID 服務擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=zh-Hant) | 使用 [Adobe Experience Cloud ID 服務擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=zh-Hant) | 使用 [Adobe Experience Cloud ID 服務擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=zh-Hant) | [單獨呼叫 ID 服務伺服器](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=zh-Hant)以取得所需的 ID |

{style=&quot;table-layout:auto&quot;}

如果在各個實施類型中有變數不一致，Adobe 會將其視為單獨的訪客。如果訪客未在您網站上跨實施類型進行無縫追蹤，最常見的原因是 ID 服務設定不正確。如需詳細資料，請參閱「ID 服務使用者指南」中的[實施方法](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html?lang=zh-Hant)。
