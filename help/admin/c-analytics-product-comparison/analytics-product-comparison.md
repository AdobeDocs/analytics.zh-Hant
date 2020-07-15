---
description: Analysis Workspace、Reports & Analytics、Ad Hoc Analysis、Report Builder、Data Warehouse 和 Data Workbench 的系統要求與比較。
title: Analytics 產品比較和需求
translation-type: tm+mt
source-git-commit: cb3948f03e65edf18b7f3c54c891b77629b41dc0
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 83%

---


# Analytics 產品比較和需求

分析工作區、報告與分析、報告建立工具、資料倉庫、資料工作台、Analytics API 2.0、資料饋送和客戶歷程分析的系統需求與比較。

如需瞭解如何挑選 Adobe Analytics 產品，請前往[此處](/help/admin/c-analytics-product-comparison/which-analytics-tool.md)。

| 產品名稱和說明連結 | [Analysis Workspace](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/reports-analytics/getting-started.html) | [Report Builder](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/zh-Hant/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html) | Analytics API 2.0 | 資料饋送 | Customer Journey Analytics |
|---|---|---|---|---|---|---|
| **存取方法** | 用於建立強大、自訂的分析專案，並讓使用者都能自行獲得深入見解的瀏覽器解決方案。 | 數位分析的瀏覽器解決方案。 | 可產生 .csv 格式報表的瀏覽器解決方案。可產生 Tableau 格式檔案。 | 用於進階分析的多頻道分析工具，例如自訂歸因模型、預測分析，以及 360 客戶分析。 |  |  |  |
| **報表劃分** | 無限制 | 最多 2 個關聯 | 最多 2 個關聯 | 執行完全擴充、無限制的劃分，依區段劃分。 | 無限制 |  |  |  |
| **區段比較** | 無限制 | 最多 2 個區段 | 無限制 （資料要求堆疊） | 1 個區段. 支援多個 (堆疊) 區段。 | 無限制 |  |  |  |
| **列輸出限制** | 400 | 200 | 50,000 | 無限制 | 可自訂 |  |  |  |
| ****&#x200B;獨特值限制 (eVar/ prop 報表中) | 500K-2MM | 500K-2MM | 500K-2MM | 無限制 | 可自訂 |  |  |  |
| **漏斗/路徑** | 是： [流失](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)/流[量](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/visualizations/flow/flow.html) | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/reports-analytics/reports.html) | 有 | 無 | 是 |  |  |  |
| **進階客戶動向分析** | Yes: [Customer Journey Analytics](https://docs.adobe.com/content/help/zh-Hant/analytics-platform/using/cja-landing.html) | 無 | 無 | 無 | 是 |  |  |  |
| **同類群組分析** | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | 無 | 無 | 無 | 是 |  |  |  |
| **進階歸因** | 是： [歸因IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution-iq.html) | 有限 - 首次/上次/線性 | 有限 - 首次/上次/線性 | 有限 - 首次/上次/線性 | 是 |  |  |  |
| **增強視覺效果選項** | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) | 無 | 是 | 無 | 是 |  |  |  |
| **可自訂配置** | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/home.html) | 是 - [控制面板](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/dashboard.html) | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/report-builder/layout/configure-the-custom-layout.html) | 依劃分或依量度排序結果。 | 是 |  |  |  |
| ****&#x200B;專案組織 (為非分析人員簡化報表) | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/curate.html) | 無 | 是 | 無 | 是 |  |  |  |
| **專案共用** | [是： 所有／任何使用者](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/curate.html) | [是： 所有／任何使用者](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/reports-analytics/scheduling.html) | 是： 所有／任何使用者 | 無 | 是 |  |  |  |
| **排程報表傳送** (Scheduled Report Delivery) | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html) | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/reports-analytics/scheduling.html) | [是](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/report-builder/t-schedule-a-data-request.html) | 是 | 是 |  |  |  |
| **系統要求** | 瀏<br>[覽器更多……](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/sys-reqs.html) | 瀏<br>[覽器更多……](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/sys-reqs.translate.html) | Windows、MS<br>[ExcelMore...](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | 需要瀏覽器和程式來開啟 .csv 檔案 (如 MS Excel)。可產生 Tableau 格式檔案。 | Windows 64 bit, good graphics adapter for OpenGL 3.2 [More...](https://docs.adobe.com/content/help/zh-Hant/data-workbench/using/install/c-data-workbench-client-install.html) |  |  |  |
| **虛擬報表套裝（報表時間處理）相容性** | 是 | 是 | 是 | 無 | 是? |  |  |  |
| **多報表套裝** | 有 | 無 | 無 | 無 | 是? |  |  |  |
| **計算量度** | 是 | 是 | 是 | 是 | 是 |  |  |  |
| **行銷渠道相容性** | 是 | 是 | 是 | ? | ? |  |  |  |
| **詳細程度** |  |  |  |  |  |  |  |  |
| **異常偵測** | 有 | 無 |  |  |  |  |  |  |
| **貢獻分析** | 有 | 無 | 無 | 無 | 是 |  |  |  |
| **區段類型** |  |  |  |  |  |  |  |  |