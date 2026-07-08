---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 13d4b15d7069a52f4953a49aa0f1f5b7cb16ae77
workflow-type: tm+mt
source-wordcount: 890
ht-degree: 63%

---

# 最新Adobe Analytics發行說明（2026年7月）

**上次更新日期**：2026年7月8日

以下發行說明涵蓋2026年7月發行期間。 Adobe Analytics 版本發行採用[持續傳遞模式](releases.md)，透過擴充性更高的分階段方式進行功能部署。 因此，這些發行說明每月會更新多次。 請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ---- |
| **子點選分析** <br/>子點選分析可讓您在比點選層級更精細的層級分析產品資料。 您可以對點選中的個別產品進行分段，而不需篩選整個點選。 <p>例如，您可以將特定產品類別分段，而不納入同一訂單中購買的所有其他產品。</p><p>如需詳細資訊，請參閱[子點選分析](/help/components/segmentation/sub-hit.md)。</p> | 7月8日 | 2026年7月底 |
| **AA 2.0 API搜尋功能指南** <br/>使用搜尋功能來[傳回報告中的維度專案子集](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters)。<p>如需詳細資訊，請參閱Adobe Developer上報表端點指南中的[搜尋功能](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/search-filters)。 | | 2026年7月1日 |
| **使用AA API自動化週期性報告** <br/>使用報表API依排程為資料管道設定自動週期性報告，並採用最新量度。 <p>如需詳細資訊，請參閱Adobe Developer上的[自動循環Analytics報表端點指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/reports/recurring)。</p> | | 2026年7月1日 |
| **AA的新擴充引數** <br/>使用新的Dimension API擴充引數來擷取配置型別、有效期、資料型別和銷售的eVar設定欄位。 <p>如需詳細資訊，請參閱Adobe Developer上的[API參考](https://developer.adobe.com/analytics-apis/docs/2.0/apis/#operation/dimensions_getDimensions)和[維度端點指南](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/dimensions/)。</p> | | 2026年7月1日 |

### Adobe Analytics 中的修正

**Activity Map**：
**Analysis Workspace**： AN-449890、AN-457527、AN-451161、AN-459034、AN-458071、AN-458398
**分類**： AN-453318、AN-456739、AN-455828、AN-455270、AN-460272、AN-459367、AN-459239、AN-458418、AN-458417
**資料摘要和Data Warehouse**： AN-456945、AN-460700
**移轉**：
**匯出**：
**Report Builder**： AN-457533、AN-453683
**報告**： AN-447692、AN-451259、AN-455713
**報告套裝**：
**排程報告**： AN-450715
**細分**：
**Other**： AN-453982、AN-455771

### 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版 Report Builder 增益集將於 2026 年 6 月淘汰。 所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](/help/analyze/report-builder/rb-overview.md)。 Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。 全新 Report Builder [功能幾乎與舊版相同](/help/analyze/report-builder/convert-workbooks.md#unsupported)，並額外提供更多便利功能和 UI 增強設計。 為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。 全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。 許多組織在為使用者提供增益集之前，須先完成內部核准流程。 請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/?lang=zh-Hant)」，以了解常見問題的解答和進一步指引。</p> |

## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。

## 延遲的功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **串流媒體服務：支援排程資料**<br/>您現在可以上傳過去串流媒體直播內容的排程資料，讓您追蹤觀看人數更輕鬆也更準確。<p>以下是支援排程資料上傳的直播內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data) | 2025 年 10 月 29 日 | 待定<p>（原計畫於2025年10月29日推出）</p> |


>[!MORELIKETHIS]
>
>* [2026年舊版發行說明](/help/release-notes/2026.md)
>* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hant)
>* [串流媒體服務發行說明](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 產品](https://business.adobe.com/tw/products/adobe-experience-cloud-products.html)的最新發行更新

