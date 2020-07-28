---
description: Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse 和 Data Workbench 的系統要求與比較。
title: Analytics 產品比較和需求
translation-type: tm+mt
source-git-commit: 22d6e88f01868e38e6de4de2efa277d5d16954d5
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 55%

---


# Analytics 產品比較和需求

本頁包含各種Adobe Analytics產品的比較： 分析工作區、報告與分析、報告建立工具、資料倉庫、資料工作台、資料饋送和Analytics API 2.0。

如需瞭解如何挑選 Adobe Analytics 產品，請前往[此處](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)。

| 產品名稱和說明連結 | [Analysis Workspace](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/reports-analytics/getting-started.html) | [Report Builder](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/zh-Hant/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html) | [資料摘要](https://docs.adobe.com/content/help/zh-Hant/analytics/export/analytics-data-feed/data-feed-overview.html) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **存取方法** | [瀏覽器](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/sys-reqs.html) | [瀏覽器](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/sys-reqs.translate.html) | [Windows版MS Excel](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | 透過瀏覽器進行設定。 支援的目的地包括FTP。 聯絡客戶服務以取得其他目的地支援。 [深入了解](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/sys-reqs.html) | [Windows 64位元](https://docs.adobe.com/content/help/zh-Hant/data-workbench/using/install/c-data-workbench-client-install.html) | 透過瀏覽器進行設定。 支援的目標包括FTP、SFTP、Azure Blob、S3。 [深入了解](https://docs.adobe.com/content/help/zh-Hant/analytics/export/analytics-data-feed/data-feed-overview.html) | REST風格的API工具。 使用Adobe I/O認證登入。 [深入了解](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **資料格式（詳細程度）** | 彙總 | 彙總 | 彙總 | ECID | 時間戳記+ ECID | 時間戳記+ ECID | 彙總 |
| **處理等級** | 完全處理 | 完全處理，並提供個 [別的即時報表](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | 完全處理，並提供個 [別的即時報表](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | 完全處理 | 完全處理 | 完全處理 | 完全處理 |
| **內含管理機器人篩選資料**<br>[瞭解詳情](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html) | 無 | 是——個別機器人報表 | 是——個別機器人報表 | 無 | 無 | 無 | 無 |
| **出現低流量（超出唯一客戶數）** 了 <br>[解詳情](https://docs.adobe.com/content/help/zh-Hant/analytics/technotes/low-traffic.html) | 是 | 是 | 是 | 無 | 無 | 無 | 是 |
| **可見的列限制（編頁前）** | 400 | 200 | 50000 | 無限制 | 無限制 | 無限制 | 50000 |
| **多個報表套裝** | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) | 是的，但有限制 | 有 | 無 | 是 | 無 | 是 |
| **劃分數** | 無限制 | 最多 2 | 最多 2 | 無限制 | 無限制 | 無限制 | 無限制，可跨多個查詢執行 |
| 「區&#x200B;**段**<br>[瞭解詳情](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) | 是 | 是 | 是 | 是的，但有限 [制](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-compatibility.html) | 有 | 無 | 是 |
| **計算量度** 更 <br>[多資訊](https://docs.adobe.com/content/help/zh-Hant/analytics/components/calculated-metrics/cm-overview.html) | 是的，有了 [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | 是 | 是 | 無 | 是 | 無 | 是的，有了 [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **行銷渠道**<br>[瞭解](https://docs.adobe.com/content/help/zh-Hant/analytics/components/marketing-channels/c-getting-started-mchannel.html) | 是 | 是 | 是 | 是 | 是 | 是- va_finder、va_closer | 是 |
| **世代分析** | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | 無 | 無 | 無 | 是 | 無 | 無 |
| **出處** | 是的，有了 [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | 有限 | 有限 | 無 | 是 | 無 | 是的，有了 [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **虛擬分析師功能**<br>[詳細資訊](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/virtual-analyst/overview.html) | 有 | 無 | 無 | 無 | 無 | 無 | 是 |
| **組織**<br>[詳細資訊](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/curate.html) | 是——專案和VRS | 無 | 無 | 無 | 無 | 無 | 是——僅限VRS |
| **專案共用**<br>[更多資訊](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | 是，具有項目角色 | 是 | 是 | 無 | 是 | 無 | 無 |
| **排程的傳送** | 是 | 是 | 是 | 是 | 是 | 是 | 無 |
| **VRS報告時間處理** 更 <br>[多資訊](https://docs.adobe.com/content/help/zh-Hant/analytics/components/virtual-report-suites/vrs-report-time-processing.html) | 有 | 無 | 無 | 無 | 無 | 無 | 是 |
