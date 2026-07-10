---
title: 追蹤不同的實施類型
description: 使用不同的實施類型，順暢地在不同的實施間追蹤訪客。
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/FM6c33rpXxzy1huu8KE0VBkfe4FGIySczmVMrprFEUY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 612
ht-degree: 47%

---

# 追蹤不同的實施類型

Adobe Analytics 實施的核心架構在所有實施類型中都是一致的。 該流程涉及定義變數，並將其編譯成傳送至 Adobe 資料收集伺服器的影像要求。 這個概念代表您可以在 AppMeasurement、Web SDK 及其在 Adobe Experience Platform 資料收集中的各自擴充功能之間，跨同一網站的不同頁面無縫切換。

Adobe 建議在所有頁面上使用相同的實施類型來保持網站實施的一致性。 但是，如果您網站的某些部分有不同的要求，您可以使用此頁面來協助確保跨頁面持續追蹤訪客。

如果您使用多種型別的實施（例如AppMeasurement和硬式編碼影像要求），請確定下列變數已正確設定並彼此相符。

>[!NOTE]
>
>所有實作型別都必須使用相同的訪客身分識別型別（舊版Analytics ID、訪客ID服務或Experience Platform Identity服務）。 Adobe建議儘可能在所有實施中使用ECID。

| 變數 | Web SDK 標記擴充功能 | 網頁SDK (Alloy) | Analytics 擴充功能 | AppMeasurement | 硬式編碼影像要求 |
|---|---|---|---|---|---|
| 報表套裝 ID | [設定資料流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure)時，將 Adobe Analytics 新增為服務 | [設定資料流](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/datastreams/configure)時，將 Adobe Analytics 新增為服務 | [設定擴充功能](https://experienceleague.adobe.com/tw/en/docs/experience-platform/tags/extensions/client/analytics/overview)時，[!UICONTROL 程式庫管理]部分底下的[!UICONTROL 報告套裝] | [`s_gi`](../vars/functions/s-gi.md)中的字串引數 | URL `pathname` 的一部分 (`/b/ss/` 之後) |
| 訪客ID服務 | 原生包含[Experience Platform Identity服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/home)；需要[`idMigrationEnabled`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/collection/js/commands/configure/idmigrationenabled)才能讀取訪客ID服務Cookie | 原生包含[Experience Platform Identity服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/identity/home)；需要[[!UICONTROL 將ECID從VisitorAPI移轉至Web SDK]](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/web-sdk/configure/identity)以讀取訪客ID服務Cookie | 使用實作[訪客ID服務](https://experienceleague.adobe.com/tw/en/docs/id-service/using/home)的[&#39;[!UICONTROL Experience Cloud ID服務]&#39;標籤延伸](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/id-service/overview) | 實作[訪客ID服務](https://experienceleague.adobe.com/tw/en/docs/id-service/using/home) (`VisitorAPI.js`) | 對訪客ID服務[&#128279;](https://experienceleague.adobe.com/zh-hant/docs/id-service/using/implementation/direct-integration)進行個別呼叫以取得所需的ID，並將`mid`納入查詢字串中 |
| Edge網域 | [設定擴充功能](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration)時的[!UICONTROL Edge網域]欄位 | [設定 Web SDK](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/commands/configure/overview) 時，`edgeDomain` 屬性 | 在[設定擴充功能](https://experienceleague.adobe.com/tw/en/docs/experience-platform/tags/extensions/client/analytics/overview)時，位於[!UICONTROL 一般]區段下的[!UICONTROL SSL追蹤伺服器] | [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md)變數 | 影像的 `hostname` 請求 URL |

>[!NOTE]
>
>AppMeasurement型實作（包括Analytics標籤擴充功能）與[Experience Platform Identity Service](https://experienceleague.adobe.com/tw/en/docs/id-service/using/home)不相容。 您必須使用最低通用分母形式的訪客身分識別，才能跨實作型別進行同步，這通常是[訪客ID服務](https://experienceleague.adobe.com/tw/en/docs/id-service/using/home) (`VisitorAPI.js`)。

如果這些變數在每種實施型別中不一致，Adobe可能會將其視為個別訪客。 如果沒有在網站上的各種實作型別間順暢地追蹤訪客，最常見的原因是訪客身分識別設定不正確。 請確定每個實作型別都能正確取得您網站上的相同ECID （`mid` [查詢字串](/help/implement/validate/query-parameters.md)）。
