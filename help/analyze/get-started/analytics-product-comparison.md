---
description: Analysis Workspace、Report Builder、Data Warehouse 與 Data Workbench 的系統需求與比較。
title: Analytics 產品比較和需求
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/VQgK6DUSlz-UA3zk-Q18-QOAI5M6xfK7KqBYwW56j6w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: af53ada8-1b7d-4929-ac91-ac971dd20ec7
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e9cb007b-c8b7-4975-bc81-11a788c535fa
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 67%

---

# Analytics 產品比較和需求

本頁包含各種 Adobe Analytics 產品的比較：Analysis Workspace、Report Builder、Data Warehouse、資料摘要和 Analytics API 2.0。

若要了解關於使用哪種 Adobe Analytics 產品的資訊，請參閱「[我應該使用哪種 Adobe Analytics 工具？](/help/analyze/get-started/which-analytics-tool.md)」。

| 產品名稱和說明連結 | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [資料摘要](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **存取方法** | [瀏覽器](/help/analyze/get-started/sys-reqs.md) | [Windows 版 MS Excel](/help/analyze/legacy-report-builder/setup/system-requirements.md) | 透過瀏覽器進行設定。 [了解更多](/help/analyze/get-started/sys-reqs.md) | 透過瀏覽器進行設定。 [了解更多](/help/export/analytics-data-feed/data-feed-overview.md) | RESTful API 工具。 使用 Adobe Developer 憑證登入。 [了解更多](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **資料顆粒度** | 彙總 | 彙總 | 彙總 | 點擊 | 彙總 |
| **可用 Experience Cloud ID (ECID)** | 否 | 無 | 是 | 是 | 無 |
| **可用時間戳記** | 否 | 否 | 無 | 是 | 無 |
| **處理層級** | 完整處理 | 完整處理，並提供獨立的[即時報表](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) | 完整處理 | 完整處理 | 完整處理 |
| **包含管理機器人篩選資料** <br> [了解更多](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | 否 | 是 - 獨立機器人報表 | 否 | 否 | 否 |
| **低流量 (超出不重複值) 出現** <br> [了解更多](/help/technotes/low-traffic.md) | 是 | 是 | 無 | 無 | 是 |
| **可見列限制 (分頁前)** | 400 | 50000 | 無限制 | 無限制 | 50000 |
| **多報告套裝** | [是](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | 是 | 無 | 是 | 無 |
| **劃分數** | 無限制 | 最多 2 | 無限制 | 無限制 | 無限制，可跨多個查詢執行 |
| **區段** <br> [了解更多](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | 是 | 是 | 是，且具有[限制](/help/export/data-warehouse/segment-compatibility.md) | 無 | 是 |
| **計算量度** <br> [了解更多](/help/components/calculated-metrics/cm-overview.md) | 是，且具有[歸因](/help/analyze/analysis-workspace/attribution/overview.md) | 是，使用 Attribution | 是 | 無 | 是，且具有[歸因](/help/analyze/analysis-workspace/attribution/overview.md) |
| **行銷管道** <br> [了解更多](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | 是 | 是 | 是 | 是 - [va_finder、va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | 是 |
| **同類群組分析** | [是](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | 是 | 無 | 否 | 否 |
| **歸因** | 是，且具有[歸因](/help/analyze/analysis-workspace/attribution/overview.md) | 有限 | 否 | 否 | 是，且具有[歸因](/help/analyze/analysis-workspace/attribution/overview.md) |
| **組織** <br> [了解更多](/help/analyze/analysis-workspace/curate-share/curate.md) | 是 - 專案和虛擬報告套裝 | 否 | 否 | 否 | 是 - 僅限虛擬報告套裝 |
| **專案共用** <br> [了解更多](/help/analyze/analysis-workspace/curate-share/share-projects.md) | 是，且具有專案角色 | 是 | 無 | 否 | 否 |
| **排程傳送** | 是 | 是 | 是 | 是 | 無 |
| **傳送目的地** | 電子郵件 | 電子郵件、FTP、SFTP、[發佈至 Microsoft PowerBI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3、Google Cloud Platform、Azure SAS、Azure RBAC 和電子郵件 | Amazon S3、Azure RBAC、Azure SAS 和 Google Cloud Platform | - |
| **虛擬報告套裝報告時間處理**<br> [了解更多](/help/components/vrs/vrs-report-time-processing.md) | 是 | 無 | 否 | 無 | 是 |
| **地理與技術報表** | 是 <p>使用中間值而非張貼欄位。 造訪首次點選邏輯是以`post_cust_hit_time_gmt`為基礎，而非`visit_page_num=1`。 如果IP在造訪期間變更、點選未依順序抵達或造訪超出月份界限，則結果可能會與其他工具不同。</p> | 是 <p>使用中間值而非張貼欄位。 造訪首次點選邏輯是以`post_cust_hit_time_gmt`為基礎，而非`visit_page_num=1`。 如果IP在造訪期間變更、點選未依順序抵達或造訪超出月份界限，則結果可能會與其他工具不同。</p> | 是 <p>使用貼文值和`visit_page_num=1`來判斷造訪的第一次點選。 將第一次點選的值套用至這些維度在造訪中的所有點選。</p> | 是 <p>使用貼文值和`visit_page_num=1`來判斷造訪的第一次點選。 將第一次點選的值套用至這些維度在造訪中的所有點選。</p> | 是 <p>使用中間值而非張貼欄位。 造訪首次點選邏輯是以`post_cust_hit_time_gmt`為基礎，而非`visit_page_num=1`。 如果IP在造訪期間變更、點選未依順序抵達或造訪超出月份界限，則結果可能會與其他工具不同。</p> |
