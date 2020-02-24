---
description: Adobe Audience Manager (AAM) 是一個功能強大的資料管理平台，可協助您從第一方、第二方/合作夥伴與第三方資料整合建立獨一無二的對象個人資料。對廣告商來說，這些對象個人資料有助於定義可用於任何數位通路的最有價值區段。
solution: Experience Cloud
title: Audience Analytics 概觀
uuid: 86ef9391-dd6a-495f-a10e-e98bc069dde4
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Audience Analytics 概觀

Adobe Audience Manager (AAM) 是一個功能強大的資料管理平台，可協助您從第一方、第二方/合作夥伴與第三方資料整合建立獨一無二的對象個人資料。對廣告商來說，這些對象個人資料有助於定義可用於任何數位通路的最有價值區段。

有了 Audiences Analytics 整合後，您可以將 AAM 對象資料，如人口資訊 (例如性別或收入等級)、心理變數資訊 (例如興趣及嗜好)、CRM 資料與廣告曝光資料，整合至 Analytics 工作流程。

## 主要優點 {#section_94816D17283349E0BA28521BE55BB868}

Audience Analytics 整合具有以下主要優點：

* 這是市場中的資料管理平台 (DMP) 和分析引擎之間的首個產品化整合。
* 區段會即時從 AAM 分享至 Analytics，以進行對象發現通知、分段及最佳化。
* 所有 AAM 區段依預設皆為共用，完整地豐富了 Analytics 中的客戶資料。
* 解決方案管理員可以透過使用者介面實現整合，僅需要變更極少量程式碼。
* 只有遵循 Audience Manager 資料匯出控制的區段才會共用。

## 運作方式 {#section_CECDF5A0FEC64264B206EFEF54F19EF2}

![](assets/mc-aud-dataflow.png)

1. 每次訪客瀏覽您的數位內容時，系統都會收集點擊數並傳送到 Analytics。
1. 有了[伺服器端轉送](/help/admin/admin/c-server-side-forwarding/ssf.md)，Analytics 收到的每次點擊都會即時自動傳送到 AAM。
1. 透過 Audience Analytics 整合，系統會針對各個點擊，在 AAM 中查找訪客的對象成員資格，並將區段 ID 清單傳回 Analytics 即時處理。

因為 AAM 區段是按相同的點擊方式插入，故此可以確定 AAM 中關於訪客的任何資料都不會遺漏，且是該點擊的最新狀態。這一點優於 AppMeasurement 外掛程式，因為外掛程式必須等到下次點擊時 (而非目前點擊) 才能提供這些區段。

此外，AAM 區段 ID 會自動分類成易記名稱，讓您不必在 Analytics 報表中辛苦查看英數字元 ID。

## 必備條件 {#section_A345DC31F7D44EAE9DC1AB53E824C0CC}

確定已具備下列必要條件：

* 您同時是 Audience Manager 和 Adobe Analytics 的客戶。
* 您是 Audience Manager 管理員。
* 您使用 Identity Service v1.5 或更新版本。
* AAM 及 Adobe Analytics 報表套裝[對應至同一個 Experience Cloud 組織](https://marketing.adobe.com/resources/help/zh_TW/mcloud/report-suite-mapping.html)。
* 您使用[伺服器端轉送](/help/admin/admin/c-server-side-forwarding/ssf.md)，並已實作[對象管理模組](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) (無 DIL 代碼) - AppMeasurement 1.5 或更新版本。

[對象分析工作流程](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md)中會說明這些必備條件。
