---
description: Adobe Audience Manager (Adobe Audience Manager)是一個功能強大的資料管理平台，可協助您從第一方、第二方/合作夥伴和第三方資料整合建立獨一無二的對象設定檔。 對廣告商來說，這些對象個人資料有助於定義可用於任何數位通路的最有價值區段。
solution: Experience Cloud
title: Audience Analytics 概觀
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 44%

---

# Audience Analytics 概觀

Adobe Audience Manager (Adobe Audience Manager)是一個功能強大的資料管理平台，可協助您從第一方、第二方/合作夥伴和第三方資料整合建立獨一無二的對象設定檔。 對廣告商來說，這些對象個人資料有助於定義可用於任何數位通路的最有價值區段。

Audience Analytics整合就緒後，您就可以將Adobe Audience Manager對象資料，例如人口資訊（例如性別或收入等級）、心理變數資訊（例如興趣和愛好）、CRM資料和廣告曝光資料整合到任何Analytics工作流程中。

>[!VIDEO](https://video.tv.adobe.com/v/25450/?quality=12)

## 主要優點 {#section_94816D17283349E0BA28521BE55BB868}

Audience Analytics 整合具有以下主要優點：

* 這是市場中的資料管理平台 (DMP) 和分析引擎之間的首個產品化整合。
* 區段可即時從Adobe Audience Manager分享至Analytics，以告知對象探索、細分和最佳化。
* 預設會共用所有Adobe Audience Manager區段，充分豐富Analytics中的客戶設定檔。
* 解決方案管理員可以透過使用者介面實現整合，僅需要變更極少量程式碼。
* 只有遵循 Audience Manager 資料匯出控制的區段才會共用。

## 運作方式 {#section_CECDF5A0FEC64264B206EFEF54F19EF2}

![](assets/mc-aud-dataflow.png)

1. 每次訪客瀏覽您的數位內容時，系統都會收集點擊數並傳送到 Analytics。
1. 有了 [伺服器端轉送](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)，Analytics收到的每次點選都會即時自動傳送至Adobe Audience Manager。
1. 透過Audience Analytics整合，系統會針對每次點選，在Adobe Audience Manager中查詢訪客的對象成員資格，並將區段ID清單傳回Analytics即時處理。

由於Adobe Audience Manager區段是按相同點選基準插入，您可以確定Adobe Audience Manager中有關訪客的任何可用資料都不會遺失，並且不會為該點選提供最新資訊。 這一點優於 AppMeasurement 外掛程式，因為外掛程式必須等到下次點擊時 (而非目前點擊) 才能提供這些區段。

此外，我們會自動將Adobe Audience Manager區段ID分類為易記名稱，因此您不必在Analytics報表中檢視英數字元ID。

## 先決條件 {#section_A345DC31F7D44EAE9DC1AB53E824C0CC}

確定已具備下列先決條件：

* 您同時是 Audience Manager 和 Adobe Analytics 的客戶。
* 您是 Audience Manager 管理員。
* 您使用 Identity Service v1.5 或更新版本。
* Adobe Audience Manager和Adobe Analytics報表套裝對應至相同的Experience Cloud組織。
* 您使用[伺服器端轉送](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)，並已實施作業[對象管理模組](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) (無 DIL 代碼) - AppMeasurement 1.5 或更新版本。

[對象分析工作流程](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md)中會說明這些先決條件。
