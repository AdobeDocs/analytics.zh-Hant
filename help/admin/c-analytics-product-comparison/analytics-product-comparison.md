---
description: Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse 和 Data Workbench 的系統要求與比較。
title: Analytics 產品比較和需求
translation-type: tm+mt
source-git-commit: 3a822c1c52a072f92a402810ec643a499c81b76d
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 54%

---


# Analytics產品比較和需求

本頁包含各種Adobe Analytics產品的比較：分析工作區、報告與分析、報告建立工具、資料倉庫、資料工作台、資料饋送和Analytics API 2.0。

如需瞭解如何挑選 Adobe Analytics 產品，請前往[此處](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)。

| 產品名稱和說明連結 | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://docs.adobe.com/content/help/zh-Hant/data-workbench/using/home.html) | [資料摘要](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **存取方法** | [瀏覽器](/help/admin/sys-reqs.md) | [瀏覽器](/help/admin/sys-reqs.md) | [Windows版MS Excel](/help/analyze/report-builder/setup/system-requirements.md) | 透過瀏覽器進行設定。 [更多詳情](/help/admin/sys-reqs.md) | [Windows 64位元](https://docs.adobe.com/content/help/zh-Hant/data-workbench/using/install/c-data-workbench-client-install.html) | 透過瀏覽器進行設定。 [更多詳情](/help/export/analytics-data-feed/data-feed-overview.md) | REST風格的API工具。 使用Adobe I/O認證登入。 [更多詳情](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **資料粒度** | 彙總 | 彙總 | 彙總 | 彙總 | 點擊 | 點擊 | 彙總 |
| **Experience Cloud ID(ECID)已推出** | 無 | 無 | 無 | 是 | 是 | 是 | 無 |
| **可用時間戳記** | 無 | 無 | 無 | 無 | 是 | 是 | 無 |
| **處理等級** | 完全處理 | 完全處理，並提供個 [別的即時報表](/help/components/c-real-time-reporting/realtime.md) | 完全處理，並提供個 [別的即時報表](/help/components/c-real-time-reporting/realtime.md) | 完全處理 | 完全處理 | 完全處理 | 完全處理 |
| **包含管理機器人篩選資料** <br> [更多詳情](/help/admin/admin/bot-removal/bot-removal.md) | 無 | 是——個別機器人報表 | 是——個別機器人報表 | 無 | 無 | 無 | 無 |
| **低流量（超出唯一客戶數）出現** <br> [更多詳情](/help/technotes/low-traffic.md) | 是 | 是 | 是 | 無 | 無 | 無 | 是 |
| **可見的列限制（編頁前）** | 400 | 200 | 50000 | 無限制 | 無限制 | 無限制 | 50000 |
| **多個報表套裝** | [是](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | 是的，但有限制 | 有 | 無 | 是 | 無 | 是 |
| **劃分數** | 無限制 | 最多 2 | 最多 2 | 無限制 | 無限制 | 無限制 | 無限制，可跨多個查詢執行 |
| **區段** <br> [更多詳情](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) | 是 | 是 | 是 | 是的，但有限 [制](/help/components/c-segmentation/seg-reference/seg-compatibility.md) | 有 | 無 | 是 |
| **計算量度** <br> [更多詳情](/help/components/c-calcmetrics/cm-overview.md) | 是的，有了 [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | 是 | 是 | 無 | 是 | 無 | 是的，有了 [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **行銷管道** <br> [更多詳情](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | 是 | 是 | 是 | 是 | 是 | 是- [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | 是 |
| **世代分析** | [是](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 無 | 無 | 無 | 是 | 無 | 無 |
| **出處** | 是的，有了 [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | 有限 | 有限 | 無 | 是 | 無 | 是的，有了 [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **虛擬分析師功能** <br> [更多詳情](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | 有 | 無 | 無 | 無 | 無 | 無 | 是 |
| **組織** <br> [更多詳情](/help/analyze/analysis-workspace/curate-share/curate.md) | 是——專案和VRS | 無 | 無 | 無 | 無 | 無 | 是——僅限VRS |
| **專案共用** <br> [更多詳情](/help/analyze/analysis-workspace/curate-share/share-projects.md) | 是，具有項目角色 | 是 | 是 | 無 | 是 | 無 | 無 |
| **排程的傳送** | 是 | 是 | 是 | 是 | 無 | 是 | 無 |
| **傳送目的地** | 電子郵件 | 電子郵件 | 電子郵件、FTP、SFTP、發 [布至Microsoft PowerBI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | 電子郵件、FTP。 聯絡客戶服務以取得其他目的地支援，包括SFTP、Azure Blob、Amazon S3 | - | FTP、SFTP、Azure Blob、Amazon S3 | - |
| **VRS報告時間處理** <br> [更多詳情](/help/components/vrs/vrs-report-time-processing.md) | 有 | 無 | 無 | 無 | 無 | 無 | 是 |
