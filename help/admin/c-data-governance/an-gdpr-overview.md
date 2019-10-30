---
description: 本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。
seo-description: 本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。
seo-title: Adobe Analytics 和 GDPR
title: Adobe Analytics 和 GDPR
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# Adobe Analytics 和 GDPR

本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。

## Adobe 概述 {#section_E582A1D77583410EBB790BB646854A2C}

> [!IMPORTANT]本文件的內容不是法律建議，且用意並非要取代法律建議。請諮詢貴公司的法律部門，以獲取有關 GDPR 的建議。

歐盟通用資料保護規範 (GDPR) 已於 2018 年 5 月 25 日生效。For more information about Adobe's response and what this means for you as an Adobe customer, see [GDPR and Your Business.](https://www.adobe.com/privacy/general-data-protection-regulation.html)

當 Adobe 向企業提供軟體和服務時， Adobe 對於其收到和儲存的任何個人資料，會代表客戶扮演資料處理者的角色，做為提供服務的一部分。身為資料處理者，Adobe會根據您公司的許可和指示（例如，如您與Adobe的合約所載）處理個人資料。

身為資料控管方，您可以決定要由 Adobe 代表您處理和儲存哪些個人資料。如果使用 Adobe Experience Cloud 解決方案，則 Adobe 可能會根據您使用的解決方案，以及您選擇傳送到 Adobe Experience Cloud 帳戶的資訊，為您託管個人資料。For a list of examples, see [Adobe Experience Cloud privacy.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

![](assets/privacy_ready.png)

## Adobe 如何處理 GDPR 資料 {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Cloud Platform (ACP) 提供整合式的解決方案，可將品牌的資料控管基礎結構連接其用於建立和管理消費者體驗的 Adobe 工具。Adobe Cloud Platform 的資料控管功能，可啟用資料控管策略與資料使用情況之間直接關聯。

請熟悉 [Adobe 如何處理 GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) 的內容，瞭解 GDPR 整備步驟，以及如何與 Adobe Experience Cloud GDPR API 整合。

## GDPR 整備與您的 Adobe Analytics 資料 {#section_9A47CDCD614C42238F6E05CFF0180195}

Adobe 瞭解您最熟悉報表套裝中的自訂資料，我們讓您能夠定義資料控管設定和偏好設定。

To that end, Adobe Analytics provides a Data Governance user interface that lets you, as the data controller, set [privacy labels](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) on your Analytics report suites and all the dimensions and metrics in those report suites. 您可以識別資料集中包含直接可識別資料或間接可識別資料的欄，以便您提交存取和刪除請求以處理該資料。對於每個請求，系統會針對對應至該請求的特定識別碼，接受在 Analytics 資料控管使用者介面中定義的標籤。

請參閱[標籤報表套裝資料](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)，以瞭解如何設定標籤的詳細資訊。

## 必備條件 {#section_3C766371CE0641C0821FE8E750E5AE0C}

* Familiarize yourself with [GDPR terminology.](/help/admin/c-data-governance/gdpr-terminology.md)
* 將您的登入公司連結至 Experience Cloud 組織 (如果尚未連結)。Contact Adobe Customer Care and refer to [Organizations and account linking.](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)
* Map any Adobe Analytics report suite that you want to set up for data governance to [your Experience Cloud organization.](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)
* 為每個報表套裝設定資料保留政策，以便接受 GDPR 刪除與存取請求。

   > [!NOTE]如果您尚未在 Adobe Analytics 中設定資料保留時間，Adobe Analytics 將無法協助您處理 GDPR API 的相關請求，例如處理一般使用者所提出的存取或刪除請求。請聯絡客戶成功案例經理，以設定資料保留時間。

* 檢查您的權限: 若要使用 Adobe Analytics 中的資料控管管理介面，您必須是 Adobe Analytics 管理員。
