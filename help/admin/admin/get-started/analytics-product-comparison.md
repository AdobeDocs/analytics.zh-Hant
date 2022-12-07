---
description: Analysis Workspace、Reports & Analytics、Report Builder、Data Warehouse 和 Data Workbench 的系統需求與比較。
title: Analytics 產品比較和需求
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 5f7aef6d972fe90f8eb750366fba184a97d1b01f
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 94%

---

# Analytics 產品比較和需求

本頁包含各種 Adobe Analytics 產品的比較：Analysis Workspace、Reports &amp; Analytics、Report Builder、Data Warehouse、Data Workbench、「資料摘要」和 Analytics API 2.0。

如需要使用哪種Adobe Analytics產品的詳細資訊，請參閱 [我該使用哪種Adobe Analytics工具？](/help/admin/admin/get-started/which-analytics-tool.md).

| 產品名稱和說明連結 | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html) | [資料摘要](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **存取方法** | [瀏覽器](/help/admin/admin/get-started/sys-reqs.md) | [瀏覽器](/help/admin/admin/get-started/sys-reqs.md) | [Windows 版 MS Excel](/help/analyze/report-builder/setup/system-requirements.md) | 透過瀏覽器進行設定。[了解更多](/help/admin/admin/get-started/sys-reqs.md) | [Windows 64 位元](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html) | 透過瀏覽器進行設定。[了解更多](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API 工具。使用Adobe Developer憑證登入。 [了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **資料粒度** | 彙總 | 彙總 | 彙總 | 彙總 | 點擊 | 點擊 | 彙總 |
| **可用 Experience Cloud ID (ECID)** | 否 | 否 | 否 | 是 | 有 | 是 | 否 |
| **可用時間戳記** | 否 | 否 | 否 | 否 | 是 | 是 | 否 |
| **處理層級** | 完整處理 | 完整處理，並提供獨立的[即時報表](/help/components/c-real-time-reporting/realtime.md) | 完整處理，並提供獨立的[即時報表](/help/components/c-real-time-reporting/realtime.md) | 完整處理 | 完整處理 | 完整處理 | 完整處理 |
| **包含管理機器人篩選資料** <br> [了解更多](/help/admin/admin/bot-removal/bot-removal.md) | 否 | 是 - 獨立機器人報表 | 是 - 獨立機器人報表 | 否 | 否 | 否 | 否 |
| **低流量 (超出不重複值) 出現** <br> [了解更多](/help/technotes/low-traffic.md) | 有 | 有 | 是 | 否 | 否 | 否 | 是 |
| **可見列限制 (分頁前)** | 400 | 200 | 50000 | 無限制 | 無限制 | 無限制 | 50000 |
| **多報表套裝** | [是](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | 是，且具有限制 | 有 | 否 | 是 | 否 | 是 |
| **劃分數** | 無限制 | 最多 2 | 最多 2 | 無限制 | 無限制 | 無限制 | 無限制，可跨多個查詢執行 |
| **區段** <br> [了解更多](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | 有 | 有 | 有 | 是，且具有[限制](/help/components/segmentation/seg-reference/seg-compatibility.md) | 有 | 否 | 是 |
| **計算量度** <br> [了解更多](/help/components/c-calcmetrics/cm-overview.md) | 是，且具有[歸因 IQ](/help/analyze/analysis-workspace/attribution/overview.md) | 有 | 是 | 否 | 是 | 否 | 是，且具有[歸因 IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **行銷管道** <br> [了解更多](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | 有 | 有 | 有 | 有 | 有 | 是 - [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | 是 |
| **同類群組分析** | [是](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 否 | 否 | 否 | 是 | 否 | 否 |
| **出處** | 是，且具有[歸因 IQ](/help/analyze/analysis-workspace/attribution/overview.md) | 有限 | 有限 | 否 | 是 | 否 | 是，且具有[歸因 IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **虛擬分析人員功能** <br> [了解更多](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | 有 | 否 | 否 | 否 | 否 | 否 | 是 |
| **組織** <br> [了解更多](/help/analyze/analysis-workspace/curate-share/curate.md) | 是 - 專案和 VRS | 否 | 否 | 否 | 否 | 否 | 是 - 僅限 VRS |
| **專案共用** <br> [了解更多](/help/analyze/analysis-workspace/curate-share/share-projects.md) | 是，且具有專案角色 | 有 | 是 | 否 | 是 | 否 | 否 |
| **排程傳送** | 有 | 有 | 有 | 是 | 否 | 是 | 否 |
| **傳送目的地** | 電子郵件 | 電子郵件 | 電子郵件、FTP、SFTP、[發佈至 Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | 電子郵件、FTP。請聯絡客戶服務以取得其他目的地支援，包括 SFTP、Azure Blob、Amazon S3 | - | FTP、SFTP、Azure Blob、Amazon S3 | - |
| **VRS 報表時間處理** <br> [了解更多](/help/components/vrs/vrs-report-time-processing.md) | 有 | 否 | 否 | 否 | 否 | 否 | 是 |
