---
title: 目前的 Adobe Analytics 發行說明
description: 檢視目前的 Adobe Analytics 發行說明
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: d89ba969-e026-48bf-927e-e9df2f1e34f3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 2fc50d801b70ee14c66725cec554b57cd117c8ee
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 53%
---
# 目前的Adobe Analytics發行說明（2026年10月）

**上次更新日期**：2026年10月7日

以下發行說明涵蓋2026年10月發行期間。 Adobe Analytics 版本發行採用[持續傳遞模式](releases.md)，透過擴充性更高的分階段方式進行功能部署。 因此，這些發行說明每月會更新多次。 請定期進行檢查。

## 新功能或增強功能 {#features}

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| ----------- | ---------- | ---- |
| **Adobe Analytics MCP伺服器的唯讀許可權**<br/>&#x200B;管理員現在可以授與使用者對Adobe Analytics MCP伺服器的唯讀存取權。 新的[!UICONTROL MCP唯讀存取]許可權專案可讓使用者存取所有唯讀工具，而不允許他們建立專案、區段或計算量度。<p>現有的[!UICONTROL MCP存取]許可權專案已重新命名為[!UICONTROL MCP完整存取]。 具有此許可權的使用者可繼續存取所有工具，包括建立、變更或刪除元件的工具。</p><p>如需詳細資訊，請參閱[Adobe Analytics MCP伺服器](https://developer.adobe.com/analytics-mcp/docs/aa/)。</p> | | 2026年10月6日 |
| **自動產生元件說明** <br/>您現在可以自動產生維度、量度、計算量度、區段和日期範圍的說明。 這可協助Workspace使用者瞭解要使用哪些元件，尤其是在具有大型元件庫的組織中。 <p>您可以產生單一元件的說明，或同時產生許多元件的說明。</p> <p>(文件連結待補充。)<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 2026年10月28日 |
| **Adobe Brand Visibility整合**<br/>&#x200B;將Adobe Brand Visibility與您組織的Adobe Analytics資料連結，以便測量AI驅動的探索如何轉化為實際的網站參與度和業務成果。<p>(文件連結待補充。)</p> | | 2026年10 |
| **CX Enterprise Coworker：在同事聊天中分析Adobe Analytics資料** <br/>Adobe CX Enterprise Coworker聊天現在可執行進階資料分析，而以前只能在Analysis Workspace中執行進階資料分析。 Co-worker Chat會存取您Adobe Analytics報表套裝中的資料，讓您探索該資料並獲得自然語言提示的答案。<p>(文件連結待補充。)</p> | 2026年10月2日 | 待定<p>（原計畫於2026年9月25日推出）</p> |

### Adobe Analytics 中的修正

**Activity Map**： AN-494609、AN-493182
**Analysis Workspace**： AN-495340、AN-494789、AN-493307、AN-468900
**分類**： AN-498043、AN-496619、AN-496468、AN-496217、AN-496133、AN-495567、AN-494651、AN-494345、AN-494312、AN-494261、AN-493645、AN-493507、AN-493336、AN-492869、AN-492812、AN-492751、AN-492750、AN-492741、AN-491032、AN-490802、AN-490796、AN-467849
**資料摘要與Data Warehouse**： AN-494937、AN-493065、AN-489796、AN-479109
**移轉**： AN-489850、AN-468014
**匯出**： AN-494337、AN-486563
**Report Builder**： AN-496602、AN-494224、AN-493737、AN-493508、AN-493505、AN-492806、AN-468981、AN-454376
**報告**： AN-493637、AN-461260
**報表套裝**： AN-496773、AN-495227、AN-494981、AN-494372、AN-494370、AN-493629
**排程報告**： AN-491103
**細分**：
**其他**： AN-496398、AN-494453、AN-492494

### 生命週期結束 (EOL) 重要通知 {#eol}

| EOL 產品或功能 | 新增或更新日期 | 說明 |
| --- | --- | --- |
| **舊版 Report Builder** | 2025 年 6 月 18 日 | 舊版Report Builder增益集已於2026年6月淘汰。 所有使用者皆應開始將其舊版工作簿升級至[新版 Report Builder](/help/analyze/report-builder/rb-overview.md)。 Adobe Analytics 和 Customer Journey Analytics 客戶皆可使用全新 Report Builder。 全新 Report Builder [功能幾乎與舊版相同](/help/analyze/report-builder/convert-workbooks.md#unsupported)，並額外提供更多便利功能和 UI 增強設計。 為了使升級過程更順暢，全新 Report Builder 包含一個簡易的工作簿轉換功能。 全新 Report Builder 僅可透過 Microsoft Store 以增益集的形式使用。 許多組織在為使用者提供增益集之前，須先完成內部核准流程。 請預留時間完成這項流程，並立即開始與您的組織合作，以確保有足夠的時間在 EOL 日期前完成工作簿升級。 |
| **Adobe Analytics API (版本 1.4)** | 2024 年 7 月 17 日 | 下列Analytics Legacy API服務將在&#x200B;**2026年8月31日**&#x200B;結束生命週期並關閉，且使用這些服務建立的任何整合功能都無法再運作：<ul><li>Adobe Analytics API (版本 1.4)</li><li>Adobe Analytics WSSE 驗證</li></ul><p>使用 Adobe Analytics API (版本 1.4) 的整合必須移轉到 [Adobe Analytics 2.0 API](https://developer.adobe.com/analytics-apis/docs/2.0/)，而 WSSE 整合必須移轉到 [Adobe Developer Console](https://developer.adobe.com/console) 中的 OAuth 型驗證通訊協定。</p><p>請參閱「[Adobe Analytics 1.4 API EOL 常見問題](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/?lang=zh-Hant)」，以了解常見問題的解答和進一步指引。</p> |

## AppMeasurement

如需 AppMeasurement 發行的最新消息，請參閱 [AppMeasurement 發行說明](https://github.com/adobe/appmeasurement/releases)。

## 延遲的功能

| 功能與說明 | [開始推出](releases.md) | [全面發佈](releases.md) |
| -----------|-----------|-----------|
| **串流媒體服務：支援排程資料**<br/>您現在可以上傳過去串流媒體直播內容的排程資料，讓您追蹤觀看人數更輕鬆也更準確。<p>以下是支援排程資料上傳的即時內容範例：</p><ul><li>FAST (免費廣告支援的電視) 平台</li><li>本地串流</li><li>現場體育賽事</li></ul><p>透過上傳排程資料，您可以追蹤上傳檔案中指定時間內播出的各個節目之觀看人數資料。 您甚至可以收集特定主題或節目區段的觀看人數資料。</p><p>無論您以何種方式實施串流媒體收集，均可使用這些功能。</p><p>過去在分析直播內容時，無法準確地將特定工作階段與特定節目相關聯，亦無法將特定工作階段與個別主題或節目區段相關聯。</p><p>如需詳細資訊，請參閱[上傳排程資料以追蹤即時內容](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/media-use-cases/track-schedule-data)。</p> | 2025 年 10 月 29 日 | 待定<p>（原計畫於2025年10月29日推出）</p> |


>[!MORELIKETHIS]
>
>* [2026年舊版發行說明](/help/release-notes/2026.md)
>* [Customer Journey Analytics 發行說明](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=zh-hant)
>* [串流媒體服務發行說明](https://experienceleague.adobe.com/zh-hant/docs/media-analytics/using/release-notes/release-notes)
>* [Adobe CX Enterprise 產品](https://business.adobe.com/tw/products/adobe-experience-cloud-products.html)的最新發行更新

