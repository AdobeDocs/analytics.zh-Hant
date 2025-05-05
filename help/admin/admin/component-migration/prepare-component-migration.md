---
description: 說明準備將元件和專案從Adobe Analytics移轉至Customer Journey Analytics的必要準備。
title: 準備將元件和專案從Adobe Analytics移轉至Customer Journey Analytics
feature: Admin Tools
exl-id: a9ff98dc-6568-428d-a8a8-faca5bc76a29
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 9%

---

# 準備將元件和專案從Adobe Analytics移轉至Customer Journey Analytics

在您組織中的任何人開始移轉專案之前(如[將元件和專案從Adobe Analytics移轉至Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md)中所述)，請完成下列章節。

## 先決條件

在專案及其相關元件準備好移轉之前，您必須先遵循Adobe Customer Journey Analytics指南中[從Adobe Analytics演化](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/aa-to-cja.html?lang=zh-Hant)的步驟。 這些步驟包括：

1. 使用下列其中一種方法將資料內嵌至Adobe Experience Platform，以便在Customer Journey Analytics檢視Adobe Analytics報表套裝資料：

   >[!NOTE]
   >
   >  當您使用WebSDK來內嵌資料時，所有結構欄位都必須手動對應。 (如需對應程式的詳細資訊，請參閱[將元件和專案從Adobe Analytics移轉至Customer Journey Analytics](/help/admin/admin/component-migration/component-migration.md))


   * 若要使用Adobe Analytics來源聯結器，您需要：

      1. [設定報告套裝以擷取至Adobe Experience Platform和Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=zh-Hant#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [擷取及使用資料](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/analytics.html?lang=zh-Hant)

   * 若要使用WebSDK，您需要：

      1. [設定報告套裝以擷取至Adobe Experience Platform和Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aa-data-in-cja.html?lang=zh-Hant#set-up-report-suites-for-ingestion-into-the-adobe-experience-platform-and-customer-journey-analytics)

      1. [透過Adobe Experience Platform Web SDK內嵌資料](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk.html?lang=zh-Hant)

1. 建立已擷取資料的[連線](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html?lang=zh-Hant)和[資料檢視](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=zh-Hant)。

1. 確保Customer Journey Analytics中的使用者已布建至資料對應的資料檢視。

   如需詳細資訊，請參閱[Customer Journey Analytics存取控制](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=zh-Hant)中Admin Console[&#128279;](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-admin/cja-access-control.html?lang=zh-Hant#customer-journey-analytics-permissions-in-admin-console)的Customer Journey Analytics許可權。

   「許可權」索引標籤是Admin Console中每個產品設定檔的一部分。 您可以將使用者新增到特定的產品設定檔。然後，將許可權指派給特定的資料檢視，並指定產品設定檔中的使用者擁有哪些許可權。

1. 以組織身分決定要如何對應元件。

   如需詳細資訊，請參閱以下章節，[決定作為組織如何對應元件](#decide-as-an-organization-how-you-will-map-components)。

## 瞭解移轉包含的內容

下表概述移轉中包含的專案和元件元素：

### 已移轉的元件元素

Dimension和量度已移轉為[將Adobe Analytics專案移轉至Customer Journey Analytics](#migrate-adobe-analytics-projects-to-customer-journey-analytics)中所述的對應程式的一部分。

Customer Journey Analytics中尚未存在的區段、日期範圍和計算量度，會根據對應的維度和量度在那裡重新建立。

|  | 「已移轉」 |
|---------|---------|
| **[所有者](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)** | Dimension和量度：否<p>區段和日期範圍： ![核取記號](assets/Smock_Checkmark_18_N.svg)</p> |
| **[共用](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension和量度：否<p>區段和日期範圍：否</p> |
| **[說明](/help/analyze/analysis-workspace/components/add-component-descriptions.md)** | Dimension和量度：否<p>區段和日期範圍： ![核取記號](assets/Smock_Checkmark_18_N.svg)</p> |
| **[標記](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)** | Dimension和量度：否<p>區段和日期範圍：否</p> |
| **[歸因（在維度上）](/help/analyze/analysis-workspace/attribution/overview.md)** | Dimension和量度：否<p>區段和日期範圍：否</p> |

{style="table-layout:auto"}

### 已移轉的專案元素

|  | 「已移轉」 |
|---------|----------|
| **[日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg) |
| **[區段](/help/components/segmentation/seg-overview.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg) |
| **[快速區段](/help/analyze/analysis-workspace/components/segments/quick-segments.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg) |
| **[維度](/help/components/dimensions/overview.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg)自動或手動對應 |
| **[量度](/help/components/metrics/overview.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg)自動或手動對應 |
| **[面板](/help/analyze/analysis-workspace/c-panels/panels.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg) |
| **[視覺效果](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg) |
| **[所有者](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg)由進行移轉的使用者定義 |
| **[組織](/help/analyze/analysis-workspace/curate-share/curate.md)** | 否 |
| **[共用](/help/analyze/analysis-workspace/curate-share/share-projects.md)** | 否 |
| **[註解](/help/analyze/analysis-workspace/components/annotations/overview.md)** | 否 |
| **[資料夾結構](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)** | 否 |
| **[說明](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg) |
| **[標記](/help/analyze/landing.md)** | 否 |
| **[我的最愛](/help/analyze/landing.md)** | 否 |
| **[排程](/help/components/scheduled-projects-manager.md)** | 否 |
| **[異常偵測](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)** | ![核取記號](assets/Smock_Checkmark_18_N.svg) |

{style="table-layout:auto"}

## 瞭解導致錯誤的不支援元素

Customer Journey Analytics不支援下列視覺效果和面板。 當這些元素在移轉前包含在專案中時，可能導致移轉失敗，或在專案移轉後發生錯誤。

將專案移轉至Customer Journey Analytics之前，請從Adobe Analytics專案中移除這些元素。 如果移轉失敗，請在重試移轉之前移除這些元素。

### 不支援的視覺效果

* [地圖](/help/analyze/analysis-workspace/visualizations/map-visualization.md)

### 不支援的面板

* [Analytics for Target (A4T)](/help/analyze/analysis-workspace/c-panels/a4t-panel.md)

* [區段比較](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md)

* [媒體平均分鐘觀眾數](/help/analyze/analysis-workspace/c-panels/average-minute-audience-panel.md)

* [下一個或上一個專案](/help/analyze/analysis-workspace/c-panels/next-previous.md)

* [頁面摘要](/help/analyze/analysis-workspace/c-panels/page-summary.md)

* [貢獻分析](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md#contribution-analysis)

## 以組織身分決定要如何對應元件

>[!IMPORTANT]
>
>移轉程式會識別Adobe Analytics專案中無法自動對應至Customer Journey Analytics中元件的元件，並允許您手動對應這些元件。
>
>**針對一個專案所做的任何對應都會套用至您整個IMS組織中的所有未來專案，無論執行移轉的使用者為何。 除非連絡客戶服務，否則無法修改或復原這些對應。**
>
>因此，您的組織在移轉任何專案之前，必須先決定維度和量度的對應方式，這一點很重要。 這樣做可避免個別管理員在僅考慮單一專案時，於穀倉中做出決策。
>
>以下是您必須手動對應的維度和量度清單（如果您的專案中存在這些維度和量度）。 我們建議您在移轉前先檢閱此清單。 如果您的專案中存在這些元件的任何一個，請立即決定將它們對應到哪些Customer Journey Analytics元件。


### 必須手動對應的Dimension

* averagepagetime
* pagetimeseconds
* singlepagevisits
* visitnumber
* timeprior
* timespent
* category
* connectiontype
* customerloyalty
* customlink
* downloadlink
* exitlink
* hitdepth
* hittype
* pathlength
* daysbeforefirstpurchase
* dayssincelastpurchase
* dayssincelastvisit
* identificationstate
* optoutreason
* persistentcookie
* returnfrequency
* searchenginenatural
* searchenginenaturalkeyword
* mobilecarrier
* monitorresolution
* surveybase
* mcaudiences
* tntbase
* targetraw


### 必須手動對應的量度

* timespentvisit
* timespentvisitor
* 重新載入
* bounces
* 跳出
* pageevents
* pageviewspervisit
* orderspervisit
* averagepagedepth
* averagetimespentonsite
* exitlinkinces
* customlinkinces
* 下載連結例項
* 黑暗訪客
* singlepagevisits
* singlevaluevisits
* visitorhomepage
* visitorsmcvisid
* pagesnotfound
* 新增參與
* time_granular
* concurrent_viewers_visitors
* concurrent_viewers_occurrences
* 問題
* estimatedpeople
* playback_time_spent_seconds
* playback_time_spent_minutes
* average_minute_audience_time_based
* average_minute_audience_media_time
* average_minute_audience_content_time
* video_length
* 目標轉換
* targetetimpression
