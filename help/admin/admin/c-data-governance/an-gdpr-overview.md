---
description: 本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。
title: Adobe Analytics 和 GDPR
feature: Data Governance
role: Admin
exl-id: 4cb19f63-119f-4853-84bf-5c1e8f9af9f0
source-git-commit: 48f1974a0c379a4e619d9a04ae80e43cce9527c1
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 87%

---

# Adobe Analytics 和 GDPR

本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。

## Adobe 概觀 {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>本文件的內容不是法律建議，且用意並非取代法律建議。請諮詢貴公司的法律部門，以獲取有關 GDPR 的建議。

歐盟通用資料保護規範 (GDPR) 已於 2018 年 5 月 25 日生效。如需有關 Adobe 回應以及這對於您身為 Adobe 客戶所代表之意義的詳細資訊，請參閱 [GDPR 和您的業務](https://www.adobe.com/privacy/general-data-protection-regulation.html)。

當 Adobe 向企業提供軟體和服務時， Adobe 對於其收到和儲存的任何個人資料，會代表客戶扮演資料處理者的角色，做為提供服務的一部分。身為資料處理者，Adobe 會根據貴公司的權限和指示 (例如依照您與 Adobe 的合約中達成的協議) 處理個人資料。

身為資料控管方，您可以決定要由 Adobe 代表您處理和儲存哪些個人資料。如果使用 Adobe Experience Cloud 解決方案，則 Adobe 可能會根據您使用的解決方案，以及您選擇傳送到 Adobe Experience Cloud 帳戶的資訊，為您託管個人資料。如需範例清單，請參閱 [Adobe Experience Cloud 隱私權](https://www.adobe.com/privacy/marketing-cloud.html#collect)。

![](assets/privacy_ready.png)

## Adobe 如何處理 GDPR 資料 {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Experience Cloud提供整合式解決方案，可連線您品牌的資料控管基礎架構，與用來建立和管理消費者體驗的Adobe工具。 Adobe Experience Cloud的資料控管功能可將資料控管原則與資料使用直接連結。

請熟悉 [Adobe 如何處理 GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) 的內容，瞭解 GDPR 整備步驟，以及如何與 Adobe Experience Cloud GDPR API 整合。

## GDPR 整備與您的 Adobe Analytics 資料 {#section_9A47CDCD614C42238F6E05CFF0180195}

Adobe 瞭解您最熟悉報表套裝中的自訂資料，我們讓您能夠定義資料控管設定和偏好設定。

為此，Adobe Analytics 提供資料控管使用者介面，可讓您以資料控管者的身分，在 Analytics 報表套裝上設定[隱私標籤](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels)，並在這些報表套裝中設定所有維度和量度。您可以識別資料集中包含直接可識別資料或間接可識別資料的欄，以便您提交存取和刪除請求以處理該資料。對於每個請求，系統會針對對應至該請求的特定識別碼，接受在 Analytics 資料控管使用者介面中定義的標籤。

如需如何設定標籤的詳細資訊，請參閱[標籤報表套裝資料](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)。

## 先決條件 {#section_3C766371CE0641C0821FE8E750E5AE0C}

* 熟悉 [GDPR 術語](/help/admin/c-data-governance/gdpr-terminology.md)。
* 將您的登入公司連結至 Experience Cloud 組織 (如果尚未連結)。請聯絡 Adobe 客戶服務，並參閱[組織與帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)。
* 為每個報表套裝設定資料保留政策，以便接受 GDPR 刪除與存取請求。

  >[!NOTE]
  >
  >如果您尚未在 Adobe Analytics 中設定資料保留時間，Adobe Analytics 將無法協助您處理 GDPR API 的相關請求，例如處理一般使用者所提出的存取或刪除請求。請聯絡您的Adobe客戶團隊，以設定您的資料保留時間。

* 檢查您的權限：若要使用 Adobe Analytics 中的資料控管管理介面，您必須是 Adobe Analytics 管理員。

