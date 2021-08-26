---
description: 概述步驟，讓您的 Adobe Analytics 實作支援資料主體的資料隱私權存取和刪除權限。
title: 隱私權工作流程
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 58%

---

# 隱私權工作流程

此工作流程概述的必要步驟，可讓您的 Adobe Analytics 實作準備好支援資料主體的資料隱私權存取和刪除權限。

1. **設定您的資料保留政策。** Adobe為資料隱私權資料存取/刪除請求服務時，需要資料保留原則。如需詳細資訊，請參閱[資料保留常見問題集](/help/technotes/data-retention.md)。
1. **請熟悉 DULE/資料隱私權標籤、Adobe Analytics ID、命名空間及 ID 擴增。** 請參 [閱Analytics變數的資料隱私](/help/admin/c-data-governance/gdpr-labels.md) 權標籤 [和標籤最佳實務](/help/admin/c-data-governance/gdpr-analytics-ids.md)。
1. **將身分、敏感程度以及資料控管標籤，指派至報表套裝中的每個變數。** 每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須仔細檢視標籤。同時檢閱啟用新解決方案整合時的標籤，因為這些整合可能會公開可能需要標籤的新變數。 重新實作行動應用程式或網站可能會變更現有變數的使用方式，因此也需要更新標籤。 請參閱[標籤報表套裝資料](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)。
1. **連線至 Adobe 資料隱私權 API 並提交存取與刪除請求。** Adobe Analytics 客戶可以透過呼叫 [Adobe Experience Cloud 資料隱私權 API](https://www.adobe.io/apis/experienceplatform/gdpr.html) 來提交個別資料隱私權請求，以便存取及刪除客戶資料。您可以提交任何 Analytics 識別碼 (如[標籤最佳做法](/help/admin/c-data-governance/gdpr-analytics-ids.md)一節中所述)，及其各自的命名空間 ID (資料來源 ID)。
1. **檢視及管理您的報表套裝資料隱私權設定。** 請參 [閱檢視報表套裝的資料控管設定](/help/admin/c-data-governance/gdpr-view-settings.md)。
