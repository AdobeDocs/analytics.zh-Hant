---
description: Analysis Workspace、Report Builder、Data Warehouse 與 Data Workbench 的系統需求與比較。
title: Analytics 產品比較和需求
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 100%

---

# Analytics 產品比較和需求

本頁包含各種 Adobe Analytics 產品的比較：Analysis Workspace、Report Builder、Data Warehouse、資料摘要和 Analytics API 2.0。

若要了解關於使用哪種 Adobe Analytics 產品的資訊，請參閱「[我應該使用哪種 Adobe Analytics 工具？](/help/analyze/get-started/which-analytics-tool.md)」。

| 產品名稱和說明連結 | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [資料摘要](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **存取方法** | [瀏覽器](/help/analyze/get-started/sys-reqs.md) | [Windows 版 MS Excel](/help/analyze/legacy-report-builder/setup/system-requirements.md) | 透過瀏覽器進行設定。[了解更多](/help/analyze/get-started/sys-reqs.md) | 透過瀏覽器進行設定。[了解更多](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API 工具。使用 Adobe Developer 憑證登入。 [了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **資料粒度** | 彙總 | 彙總 | 彙總 | 點擊 | 彙總 |
| **可用 Experience Cloud ID (ECID)** | 否 | 否 | 是 | 是 | 否 |
| **可用時間戳記** | 否 | 否 | 否 | 是 | 否 |
| **處理層級** | 完整處理 | 完整處理，並提供獨立的[即時報表](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) | 完整處理 | 完整處理 | 完整處理 |
| **包含管理機器人篩選資料** <br> [了解更多](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | 否 | 是 - 獨立機器人報表 | 否 | 否 | 否 |
| **低流量 (超出不重複值) 出現** <br> [了解更多](/help/technotes/low-traffic.md) | 有 | 是 | 否 | 否 | 是 |
| **可見列限制 (分頁前)** | 400 | 50000 | 無限制 | 無限制 | 50000 |
| **多報告套裝** | [是](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | 有 | 否 | 是 | 否 | 是 |
| **劃分數** | 無限制 | 最多 2 | 無限制 | 無限制 | 無限制，可跨多個查詢執行 |
| **區段** <br> [了解更多](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | 有 | 有 | 是，且具有[限制](/help/components/segmentation/seg-reference/seg-compatibility.md) | 無 | 是 |
| **計算量度** <br> [了解更多](/help/components/calculated-metrics/cm-overview.md) | 是，且具有[歸因](/help/analyze/analysis-workspace/attribution/overview.md) | 是，使用 Attribution | 有 | 無 | 是，且具有[歸因](/help/analyze/analysis-workspace/attribution/overview.md) |
| **行銷管道** <br> [了解更多](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | 有 | 有 | 有 | 是 - [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | 是 |
| **同類群組分析** | [是](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 有 | 否 | 否 | 否 |
| **歸因** | 是，且具有[歸因](/help/analyze/analysis-workspace/attribution/overview.md) | 有限 | 否 | 否 | 是，且具有[歸因](/help/analyze/analysis-workspace/attribution/overview.md) | 否 |
| **組織** <br> [了解更多](/help/analyze/analysis-workspace/curate-share/curate.md) | 是 - 專案和虛擬報告套裝 | 否 | 否 | 否 | 是 - 僅限虛擬報告套裝 |
| **專案共用** <br> [了解更多](/help/analyze/analysis-workspace/curate-share/share-projects.md) | 是，且具有專案角色 | 有 | 否 | 否 | 否 |
| **排程傳送** | 有 | 有 | 有 | 是 | 否 |
| **傳送目的地** | 電子郵件 | 電子郵件、FTP、SFTP、[發佈至 Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3、Google Cloud Platform、Azure SAS、Azure RBAC 和電子郵件 | Amazon S3、Azure RBAC、Azure SAS 和 Google Cloud Platform | - |
| **虛擬報告套裝報告時間處理**<br> [了解更多](/help/components/vrs/vrs-report-time-processing.md) | 有 | 否 | 否 | 否 | 是 |
