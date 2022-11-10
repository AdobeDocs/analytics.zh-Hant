---
description: 概述步驟，讓您的 Adobe Analytics 實作支援資料主體的資料隱私權存取和刪除權限。
title: 隱私權工作流程
feature: Privacy
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: ht
source-wordcount: '280'
ht-degree: 100%

---

# 隱私權工作流程

此工作流程概述的必要步驟，可讓您的 Adobe Analytics 實作準備好支援資料主體的資料隱私權存取和刪除權限。

1. **設定您的資料保留政策。** Adobe 需要資料保留政策才能服務資料隱私相關的資料存取/刪除請求。 如需詳細資訊，請參閱[資料保留常見問答](/help/technotes/data-retention.md)。
1. **請熟悉 DULE/資料隱私標籤、Adobe Analytics ID、命名空間及 ID 擴增。** 請參閱 [Analytics 變數的資料隱私標籤](/help/admin/c-data-governance/gdpr-labels.md)和[標籤最佳做法](/help/admin/c-data-governance/gdpr-analytics-ids.md)。
1. **將身分識別、敏感度及資料控管標籤指派至報表套裝中的每個變數。** 每次建立新報表套裝或在現有報表套裝內啟用新變數時，都必須仔細檢閱標籤。 啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。 重新實作行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。 請參閱[標記報表套裝資料](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)。
1. **連線至 Adobe 資料隱私 API 並提交存取與刪除請求。** Adobe Analytics 客戶可以透過呼叫 [Adobe Experience Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html) 來提交個別資料隱私請求，以便存取及刪除客戶資料。 您可以在要求中提交任何 Analytics 識別碼 (如[標籤最佳做法](/help/admin/c-data-governance/gdpr-analytics-ids.md)一節中所述)，連同其各自的命名空間 ID (資料來源 ID)。
1. **檢視及管理您的報表套裝資料隱私設定。** 請參閱[檢視報表套裝的資料控管設定](/help/admin/c-data-governance/gdpr-view-settings.md)。
