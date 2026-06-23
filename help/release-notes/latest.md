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
source-git-commit: 6adcad3efbe3c7f38ba8b15f835d700861fd2209
workflow-type: tm+mt
source-wordcount: 573
ht-degree: 90%

---

# 最新Adobe Analytics發行說明（2026年6月）

**上次更新日期**：2026年6月22日

以下發行說明涵蓋2026年6月發行期間。 Adobe Analytics 版本發行採用[持續傳遞模式](releases.md)，透過擴充性更高的分階段方式進行功能部署。 因此，這些發行說明每月會更新多次。 請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ---- |
| **Adobe Analytics 中的歷程畫布**<br/>歷程畫布是一種 Analysis Workspace 的視覺化圖表，透過分析使用者如何完成或退出歷程，幫助您深入了解定義的使用者歷程。 本效果可讓您建立由節點和箭頭組成且可彈性調整的圖表，用來呈現歷程中事件、維度項目和區段的任何組合。 資料會在您拖曳節點到畫布上或重新排列歷程的事件和條件時更新。<p>歷程畫布之前僅適用於 Customer Journey Analytics。</p><p>若要了解更多關於 Adobe Analytics 內歷程畫布的資訊，請參閱[歷程畫布概觀](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)。 </p><p>若要了解如何在 Adobe Analytics 建置歷程畫布視覺化圖表，請參閱[設定歷程畫布](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)。</p> | 2026 年 5 月 18 日 | 2026 年 6 月 5 日 |

### Adobe Analytics 中的修正

**Activity Map**：
**Analysis Workspace**： AN-452009、AN-450375、AN-449870、AN-450814、AN-450698
**分類**：
**資料摘要和Data Warehouse**：
**移轉**：
**匯出**：
**Report Builder**： AN-440912
**報告**： AN-423516
**報表套裝**： AN-455684
**排程報告**：
**細分**：
**其他**：


### 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版 Report Builder 增益集將於 2026 年 6 月淘汰。 所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](/help/analyze/report-builder/rb-overview.md)。 Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。 全新 Report Builder [功能幾乎與舊版相同](/help/analyze/report-builder/convert-workbooks.md#unsupported)，並額外提供更多便利功能和 UI 增強設計。 為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。 全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。 許多組織在為使用者提供增益集之前，須先完成內部核准流程。 請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | **2026 年 8 月 12 日**，以下 Analytics 舊版 API 服務將終止並關閉，目前使用這些服務建置的整合將停止運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/?lang=zh-Hant)」，以了解常見問題的解答和進一步指引。</p> |


## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。


>[!MORELIKETHIS]
>
>* [2026年舊版發行說明](/help/release-notes/2026.md)
>* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html)
>* [串流媒體服務發行說明](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 產品](https://business.adobe.com/products/adobe-experience-cloud-products.html)的最新發行更新
