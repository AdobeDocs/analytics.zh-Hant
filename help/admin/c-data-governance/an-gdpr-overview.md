---
description: 本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。
seo-description: 本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。
seo-title: Adobe Analytics 和 GDPR
title: Adobe Analytics 和 GDPR
uuid: 16fd5af8-9148-1e09-ad54-9e3 cdd2 b3 c6 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Adobe Analytics 和 GDPR

本文件說明您需要在 Adobe Analytics 中執行哪些操作，以支援資料主體的 GDPR 存取和刪除權限。

## Adobe 概述 {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>本文件的內容不是法律建議，且用意並非要取代法律建議。請諮詢貴公司的法律部門，以獲取有關 GDPR 的建議。

歐盟通用資料保護規則(GDPR)於2018年月25日生效。如需有關 Adobe 回應以及這對於您身為 Adobe 客戶所代表之意義的詳細資訊，請參閱 [GDPR 和您的業務](https://www.adobe.com/privacy/general-data-protection-regulation.html)。

當 Adobe 向企業提供軟體和服務時， Adobe 對於其收到和儲存的任何個人資料，會代表客戶扮演資料處理者的角色，做為提供服務的一部分。身為資料處理者，Adobe 會根據貴公司的權限和指示 (例如，依照您與 Adobe 的合約規定) 處理個人資料。

身為資料掌控者，您可以自行決定Adobe處理和儲存的個人資料。如果使用 Adobe Experience Cloud 解決方案，則 Adobe 可能會根據您使用的解決方案，以及您選擇傳送到 Adobe Experience Cloud 帳戶的資訊，為您託管個人資料。如需範例清單，請參閱 [Adobe Experience Cloud 隱私權](https://www.adobe.com/privacy/marketing-cloud.html#collect)。

![](assets/gdpr_ready.png)

## Adobe 如何處理 GDPR 資料 {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Cloud Platform (ACP) 提供整合式的解決方案，可將品牌的資料控管基礎結構連接其用於建立和管理消費者體驗的 Adobe 工具。Adobe Cloud Platform 的資料控管功能，可啟用資料控管策略與資料使用情況之間直接關聯。

請熟悉 [Adobe 如何處理 GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) 的內容，瞭解 GDPR 整備步驟，以及如何與 Adobe Experience Cloud GDPR API 整合。

## GDPR 整備與您的 Adobe Analytics 資料 {#section_9A47CDCD614C42238F6E05CFF0180195}

Adobe 瞭解您最熟悉報表套裝中的自訂資料，我們讓您能夠定義資料控管設定和偏好設定。

為此，Adobe Analytics 提供資料控管使用者介面，可讓您以資料控管者的身分，在 Analytics 報表套裝上設定[隱私標籤](../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2)，並在這些報表套裝中設定所有維度和量度。您可以識別資料集中包含直接可識別資料或間接可識別資料的欄，以便您提交存取和刪除請求以處理該資料。對於每個請求，系統會針對對應至該請求的特定識別碼，接受在 Analytics 資料控管使用者介面中定義的標籤。

請參閱[標籤報表套裝資料](../../admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731)，以瞭解如何設定標籤的詳細資訊。

## 必備條件 {#section_3C766371CE0641C0821FE8E750E5AE0C}

* 熟悉 [GDPR 術語](../../admin/c-data-governance/gdpr-terminology.md#concept_83C744A9D077476BAD8F8492DF68EBD7)。
* 將您的登入公司連結至 Experience Cloud 組織 (如果尚未連結)。請聯絡 Adobe 客戶服務，並參閱[組織與帳戶連結](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)。
* 將您想要為資料控管設定的任何 Adobe Analytics 報表套裝對應到[您的 Experience Cloud 組織](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)。
* 為每個報表套裝設定資料保留政策，以便接受 GDPR 刪除與存取請求。

   >[!NOTE]
   >
   >如果未在Adobe Analytics中設定資料保留期間，Adobe Analytics無法協助您處理GDPR API的處理要求，也無法處理您從使用者收到的存取或刪除要求。請聯絡客戶成功案例經理，以設定資料保留時間。

* 檢查您的權限: 若要使用 Adobe Analytics 中的資料控管管理介面，您必須是 Adobe Analytics 管理員。

