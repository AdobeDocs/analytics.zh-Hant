---
description: 有關 Adobe Analytics 的一般概觀資訊，包括 Analytics 介面資訊，以及管理員、分析師、使用者和開發人員快速入門資訊。
title: 管理員、分析師、一般使用者和開發人員快速入門
feature: Analytics Basics
exl-id: 11800de5-224a-4bd2-8cb1-a6318925db71
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '1672'
ht-degree: 99%

---

# 管理員、分析師、一般使用者和開發人員快速入門

一般組織的 Adobe Analytics 使用者有 4 種類型：

* **管理員：**&#x200B;實作和設定 Adobe Analytics。

* **分析師：**&#x200B;使用 Analysis Workspace 設定專案和建立分析

* **一般使用者：**&#x200B;透過建立自己的分析或與分析師合作建立分析，取得有關客戶的可操作分析

* **開發人員：**&#x200B;使用 Adobe Analytics 2.0 API 可直接呼叫 Adobe 伺服器來執行幾乎所有可在使用者介面中執行的動作，例如建立報告以進行探索、取得深入分析或回答有關資料的重要問題。

以下資訊概觀了每個使用者如何開始使用 Adobe Analytics。

## 新管理員快速入門

Analytics 管理員負責選擇最適合其組織的實作方法。

實作 Adobe Analytics 後，管理員需要執行各種設定任務，以確保分析師和一般使用者可充分利用 Adobe Analytics 功能。管理員還應定期監控其 Analytics 環境，以確保系統執行效率。

### 確定應收集的資料類型

Adobe Analytics 可讓您從多種管道類型收集資料並將其整合在一起，以提供有意義、即時的客戶分析。

以下是一些可在其中收集資料的受支援管道：

* 行動電話

* 物聯網

* TV

* 語音助理

* 聯網汽車

* 還有更多 (定期加入新的支援管道)

您選擇的[實作方法](/help/implement/home.md)決定了可以收集的資料類型。

### 實作 Adobe Analytics

在您的網站或行動應用程式上實作 Adobe Analytics 時，有多種實作方法可使用。

如需每個可用方法的資訊，請參閱[實作 Adobe Analytics](/help/implement/home.md)。

| | 實作方法 |
|---------|---------|
| **網站** | <ul><li>Web SDK 擴充功能 (建議)</li><li>Web SDK</li><li>Analytics 擴充功能</li><li>舊版 JavaScript</li></ul> |
| **行動應用程式** | <ul><li>Mobile SDK 擴充功能 (建議)</li><li>Analytics 擴充功能</li></ul> |

{style="table-layout:auto"}

### 設定 Adobe Analytics

Analytics 管理員應先完成以下任務，再將 Adobe Analytics 提供給組織內的使用者：

| 任務 | 預定用途 | 詳細資訊 |
|---------|----------|---------|
| 定義管理員角色 | Adobe Analytics 支援各種類型的管理員 | [Adobe Analytics 中的管理員角色](/help/admin/admin-console/admin-roles-in-analytics.md) |
| 定義權限 | Analytics 管理員需要在 Admin Console 為 Adobe Analytics、報告套裝工具和 Analytics 工具指派產品設定檔。 | [Admin Console 中的 Analytics 權限](/help/admin/admin-console/permissions/analytics-tools.md) |
| 設定報告套裝並定義公司設定 | 報告套裝是 Adobe Analytics 用來產生報告的獨立資料單位。<p>管理員也可以設定[虛擬報告套裝](/help/components/vrs/vrs-about.md)以進一步分段資料。</p> | <ul><li>[建立報告套裝](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md)</li><li>[公司設定概觀](/help/admin/tools/company/c-company-settings.md)</li></ul> |
| 匯入資料 | Adobe Analytics 資料來源可讓您匯入更多重要的線上或離線資料以用於報告。 | [資料來源概觀](/help/import/data-sources/overview.md) |
| 使用分類對資料進行分類 | 分類允許您對資料進行分類，以更好地利用變數，從而將更多內容包含到單一變數中。 | [分類概觀](/help/components/classifications/classifications-overview.md) |
| 管理元件 | 使用資料字典和每個元件類型的管理區域來定義您的 Analytics 實作中可使用哪些元件，以及核准哪些元件供您的組織使用。<p>這應該持續進行，以確保組織使用者可以有效率地運用元件。 </p> | <ul><li>[資料字典概觀](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)</li><li>[計算量度管理器](/help/components/calculated-metrics/workflow/cm-manager.md)</li><li>[管理區段](/help/components/segmentation/segmentation-workflow/seg-manage.md)</li><li>[建立自訂日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md)</li></ul> |
| 異常偵測 | 「異常偵測」提供一種統計方法，以判斷指定的量度和先前的資料比較有何變更。 | [異常偵測概觀](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| 貢獻分析 | 貢獻分析會探索您資料中的隱藏模式，說明統計異常並識別聚合客群細分群體間非預期客戶動作、界外值、選定量度突升或突降背後的關聯。 | [貢獻分析概觀](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis) |
| Analytics 分段 | 可讓您建立、管理、共用功能強大且目標專一的客群細分群體，以及將其套用到使用 Analytics 功能、Adobe Experience Cloud、Adobe Target 和其他整合式 Adobe 產品的報告。 | [Analytics 分段](/help/components/segmentation/seg-home.md) |
| 將對象發佈到 Audience Manager | Adobe Audience Manager 是一個功能強大的資料管理平台，可協助您從第一方、第二方 (合作夥伴) 與第三方資料整合建置不重複對象輪廓。 | [Audience Analytics 概觀](/help/integrate/c-audience-analytics/mc-audiences-aam.md) |
| 整合 | 您可以在 Adobe Analytics 中顯示來自其他應用程式的資訊。 <p>以下是一些常見整合：</p><ul><li><a href="/help/analyze/analysis-workspace/c-panels/a4t-panel.md">目標分析</a></li><li><a href="https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=zh-Hant">串流媒體服務</a></li> | [Analytics 整合](/help/integrate/home.md) |

{style="table-layout:auto"}

### 監控 Adobe Analytics

有多種功能可協助您監控 Adobe Analytics 環境。

Analytics 管理員應了解以下可協助監控 Analytics 環境重要方面的功能：

| 任務 | 預定用途 | 詳細資訊 |
|---------|----------|---------|
| 報告活動管理員 | 報告活動管理器可讓您查看組織中每個報告套裝的報告容量。它提供報告使用量的詳細可見度，並幫助您在尖峰報告期間輕鬆診斷和修正容量問題。 | [報告活動管理員](/help/admin/tools/reporting-activity-manager/reporting-activity.md) |
| 伺服器呼叫使用量 | 伺服器呼叫又稱為「點擊」或「影像要求」，是有關資料傳送到 Adobe 伺服器進行處理的一項實例。「伺服器呼叫使用量」儀表板，用於追蹤伺服器呼叫耗用量資料，並將其與合約限制進行比較。您可以設定警報以避免使用過量。 | [伺服器呼叫使用量概觀](/help/admin/tools/server-call-usage/overage-overview.md) |
| 記錄檔 | 記錄檔可協助您查看使用者何時登入、其使用情形、存取權、報告套裝以及管理員變更。 | [記錄檔](/help/admin/tools/logs.md) |

{style="table-layout:auto"}

## 分析師快速入門

雖然組織中的任何人都可以使用 Adobe Analytics 來獲取有關跨網站和應用程式之客戶行為的可操作分析，但 Adobe Analytics 在設計時就考慮到了資料分析師的需求。

以下是分析師應熟悉的主要任務和功能，以便充分利用 Adobe Analytics 和 Analysis Workspace 的強大功能。

| 功能 | 預定用途 | 詳細資訊 |
|---------|----------|---------|
| 在 Analysis Workspace 中建置和共用專案 | Analysis Workspace 是彈性的瀏覽器工具，可協助您快速建立分析及分享見解。您可以使用拖放式操作介面建立分析、新增視覺效果以生動呈現資料、組織資料集、與組織中的任何人共用及排程專案。<p>資料分析師通常負責在 Analysis Workspace 中為其組織內的使用者建立專案。</p><p>建立專案後，分析師將這些專案分享給其組織中要求資料的[一般使用者](#end-users) (非分析師)，並協助他們了解如何解譯資料。</p> | <ul><li>[建立專案](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md)</li><li>[共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md)</li></ul> |
| 歸因 | 分析師可以透過在 Analysis Workspace 中採用各種歸因模型和回顧期間，自訂維度項目獲得成功事件評分的方式。<p>線性歸因模型會將相等的評分歸給每個帶來轉換的接觸點，而首次接觸則會將全部的評分歸給第一個接觸點。還有許多其他歸因模型可用，包括演算法模型，該模型使用統計技術來動態決定最佳評分配置。 </p> | [歸因模型與回顧期間](/help/analyze/analysis-workspace/attribution/models.md) |
| 異常偵測 | Analysis Workspace 中的統計建模透過分析量度並確定值的下限、上限和預期範圍，自動找出資料中意外的趨勢。當發生意外的尖峰或下降時，系統會在報告中發出警報。 | [異常偵測概觀](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) |
| 貢獻分析 | 使用 Analysis Workspace 探索您資料中的隱藏模式，解釋統計異常並識別客群細分群體間非預期客戶動作、界外值、量度突升或突降背後的關聯。 | [異常偵測](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)中的[貢獻分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)概觀 |
| 警報 | 根據資料異常以及在單一警報中擷取多個量度的「堆疊」警報來建立和管理警報。 | [警報概觀](/help/components/alerts/alerts-overview.md) |
| 資料匯出 | Data Warehouse 和資料摘要可讓您將資料匯出到各種雲端目的地，例如 Google Cloud Platform、Azure RBAC、Azure SAS 和 Amazon S3。 | [Analytics 匯出指南](/help/export/home.md) |
| Activity Map | Activity Map 是一種 Adobe Analytics 應用程式，專門設計來使用視覺化覆蓋圖為連結活動進行排名，並提供即時分析儀表板來監控網頁的觀眾參與情形。<p>Activity Map 可讓您設定不同的視圖，以直觀地識別客戶活動的加速情況、量化行銷計劃並根據客群需求和行為採取行動。</p> | [Activity Map](/help/analyze/activity-map/overview.md) |
| Report Builder |  Report Builder 是 Microsoft Excel 的增益集。Report Builder 能讓您根據插入 Excel 工作表中的 Adobe Analytics 資料，建置自訂請求。這些請求可動態參考工作表中的儲存格，而您可以更新及自訂 Report Builder 展示資料的方式。 | [Report Builder](/help/analyze/report-builder/rb-overview.md) |

<!-- * Realtime reporting? -->

## 一般使用者快速入門

非專業分析師的一般使用者可以與組織中的分析師合作，充分利用 Adobe Analytics 和 Analysis Workspace 的全部功能，或是學習 Analysis Workspace 的基礎知識，以便開始獲得有關客戶的可操作分析。

### 與分析師合作

通常，組織中有興趣詳細了解各個網站客戶行為的使用者不是專業分析師。

理想情況下，這些使用者應該與組織內的[分析師](#analysts)合作以完成以下工作：

1. 透過向分析師解釋他們希望了解客戶哪方面資訊來定義分析需求。

1. 檢視分析以確保它們達到目標。

1. 討論從分析中獲得的資料。

1. 隨時間視需要修改分析。

### 在 Analysis Workspace 中建立分析

您不必成為資料分析師，即可從 Adobe Analytics 獲得可操作分析。

某些使用者可能會發現在 Analysis Workspace 中建立專案和解釋如何解譯資料時，與資料分析師合作很有幫助 (如[與分析師合作](#work-with-analysts)文中所述)；其他使用者可能會覺得自己建置專案和解譯資料比較輕鬆。

Analysis Workspace 可讓您快速建置分析以收集深入見解，然後與其他人分享這些深入見解。透過拖放瀏覽器介面，您可以建立分析、新增視覺效果以生動呈現資料、組織資料集，以及與組織中您選擇的任何人共用和排程專案。

如需了解如何在 Analysis Workspace 中建立分析，請參閱 [Analysis Workspace 概觀](/help/analyze/analysis-workspace/home.md)。

## 開發人員快速入門 

[使用 Analytics API 就能直接呼叫 Adobe 的伺服器，執行幾乎所有使用者介面中可以執行的動作。](https://developer.adobe.com/analytics-apis/docs/2.0/)

您可以建立報告來探索、取得深入分析，或是回答資料相關的重要問題。您也可以管理 Adobe Analytics 的元件，例如建立區段或計算量度。

>[!MORELIKETHIS]
>
>[建立解決方案設計文件](/help/implement/prepare/solution-design.md)
>
