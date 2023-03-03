---
description: 本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 CCPA 存取和刪除權限。
title: Adobe Analytics 和 CCPA
feature: Data Governance
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
source-git-commit: 297269f2ebf88d722eaf21ce8919ce28bb6abdc7
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 97%

---

# Adobe Analytics 和 CCPA

本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 CCPA 存取和刪除權限。

## Adobe 概觀

>[!IMPORTANT]
>
>本文件的內容不是法律建議，且用意並非取代法律建議。請諮詢貴公司的法律部門，以獲取有關 CCPA 的建議。

加州消費者隱私法 (CCPA) 將於 2020 年 1 月 1 日生效。如需有關 Adobe 回應以及這對於您身為 Adobe 客戶所代表之意義的詳細資訊，請參閱 [Adobe 隱私權中心](https://www.adobe.com/tw/privacy.html)。

當 Adobe 向企業提供軟體和服務時， Adobe 對於其收到和儲存的任何個人資料，會代表客戶扮演資料處理者的角色，做為提供服務的一部分。身為資料處理者，Adobe 會根據貴公司的權限和指示 (例如依照您與 Adobe 的合約中達成的協議) 處理個人資料。

身為資料控管方，您可以決定要由 Adobe 代表您處理和儲存哪些個人資料。如果使用 Adobe Experience Cloud 解決方案，則 Adobe 可能會根據您使用的解決方案，以及您選擇傳送到 Adobe Experience Cloud 帳戶的資訊，為您託管個人資料。如需範例清單，請參閱 [Adobe Experience Cloud 隱私權](https://www.adobe.com/tw/privacy/marketing-cloud.html#collect)。

## Adobe 如何處理 CCPA 資料

Adobe Cloud Platform (ACP) 提供整合式的解決方案，可將品牌的資料控管基礎結構連接其用於建立和管理消費者體驗的 Adobe 工具。Adobe Cloud Platform 的資料控管功能，可啟用資料控管策略與資料使用情況之間直接關聯。

請熟悉 [Adobe 如何處理 GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) 的內容，瞭解隱私權整備步驟，以及如何與 Adobe Experience Cloud 隱私權服務 API 整合。

## CCPA 整備與您的 Adobe Analytics 資料

Adobe 瞭解您最熟悉報表套裝中的自訂資料，我們讓您能夠定義資料控管設定和偏好設定。為此，Adobe Analytics 提供資料控管使用者介面，可讓您以資料控管者的身分，在 Analytics 報表套裝上設定[隱私標籤](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md#data-governance-labels)，並在這些報表套裝中設定所有維度和量度。您可以識別資料集中包含直接可識別資料或間接可識別資料的欄，以便您提交存取和刪除請求以處理該資料。對於每個請求，系統會針對對應至該請求的特定識別碼，接受在 Analytics 資料控管使用者介面中定義的標籤。

請參閱[標籤報表套裝資料](/help/admin/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)，以瞭解如何設定標籤的詳細資訊。

## 先決條件

* 熟悉 [GDPR 術語](/help/admin/c-data-governance/gdpr-terminology.md)。
* 將您的登入公司連結至 Experience Cloud 組織 (如果尚未連結)。請聯絡 Adobe 客戶服務，並參閱[組織與帳戶連結](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)。
* 為每個報表套裝設定資料保留政策，以便接受 CCPA 刪除與存取請求。

   若未設定資料保留時間，Adobe Analytics 就無法協助您處理隱私權服務 API 的相關請求，亦即無法處理一般使用者所提出的存取或刪除請求。請連絡您的Adobe帳戶團隊，以設定您的資料保留期。

* 檢查您的權限：若要使用 Adobe Analytics 中的資料控管管理介面，您必須是 Adobe Analytics 管理員。
* 請考慮實施[「同意管理變數」](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)以追蹤點擊層級的同意狀態。
