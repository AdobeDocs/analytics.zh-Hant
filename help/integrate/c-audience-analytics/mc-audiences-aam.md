---
description: Adobe Audience Manager (Adobe Audience Manager)是一個功能強大的資料管理平台，可協助您從第一方、第二方/合作夥伴及第三方資料整合建立獨一無二的對象設定檔。 對於廣告商而言，這些受眾設定檔可協助定義用於任何數位頻道的最具價值區段。
solution: Experience Cloud
title: Audience Analytics 概觀
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
TQID: https://experienceleague.adobe.com/WPB1fEJx1MaWpUNRCZ48ghAVyKyc5IwoGOdgQQ-tPhI
product_v2: id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2: id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: df401a2a-327d-468c-a5e4-b7b7ccd071a0id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 522
ht-degree: 15%

---

# Audience Analytics 概觀

Adobe Audience Manager (Adobe Audience Manager)是一個功能強大的資料管理平台，可協助您從第一方、第二方/合作夥伴及第三方資料整合建立獨一無二的對象設定檔。 對於廣告商而言，這些受眾設定檔可協助定義用於任何數位頻道的最具價值區段。

Audience Analytics整合就緒後，您就可以將Adobe Audience Manager對象資料，例如人口資訊（例如性別或收入等級）、心理變數資訊（例如興趣和嗜好）、CRM資料以及廣告曝光數資料，整合至任何Analytics工作流程中。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/audience-manager/audience-analytics-integrate-aam-segments-into-analytics){target="_blank"}。

>[!ENDSHADEBOX]


## 主要優點 {#benefits}

Audience Analytics 整合具有以下主要優點：

* 這是資料管理平台(DMP)與Marketplace分析引擎之間的首次產品化整合。
* 區段可即時從Adobe Audience Manager共用至Analytics，以告知對象探索、細分和最佳化。
* 預設會共用所有Adobe Audience Manager區段，充分豐富Analytics中的客戶設定檔。
* 解決方案管理員可透過使用者介面啟用整合，只需最少的程式碼變更即可。
* 只有符合Audience Manager資料匯出控制的區段才會共用。

## Audience Analytics的運作方式 {#works}

![](assets/mc-aud-dataflow.png)

1. 每次訪客造訪您的數位財產時，系統都會收集點選並傳送至Analytics。
1. 透過[伺服器端轉送](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)，Analytics收到的每次點選都會即時自動傳送至Adobe Audience Manager。
1. 透過Audience Analytics整合，系統會針對各個點選，在Adobe Audience Manager中查詢訪客的對象成員資格，並將區段ID清單傳回Analytics即時處理。

由於Adobe Audience Manager區段是在相同點選的基礎上插入，因此您可以確定Adobe Audience Manager中有關訪客的任何可用資料都不會遺失，並且不會為該點選提供最新資訊。 此功能比AppMeasurement外掛程式優秀，因為外掛程式只能在下一次點選（而非目前點選）時使用那些區段。

此外，Adobe Audience Manager區段ID會自動分類成易記名稱，讓您不必在Analytics報表中辛苦檢視英數字元ID。

## 先決條件 {#prerequisites}

確定已具備下列先決條件：

* 您同時是Audience Manager和Adobe Analytics的客戶。
* 您是Audience Manager管理員。
* 您使用身分識別服務 v1.5 或更新版本。
* Adobe Audience Manager和Adobe Analytics報表套裝對應至同一個Experience Cloud組織。
* 您使用[伺服器端轉送](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)，並已實施作業[客群管理模組](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html) (無 DIL 代碼) - AppMeasurement 1.5 或更新版本。

[客群分析工作流程](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md)中會說明這些先決條件。
