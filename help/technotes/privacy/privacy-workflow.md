---
description: 概述步驟，讓您的 Adobe Analytics 實作支援資料主體的資料隱私權存取和刪除權限。
title: 隱私權工作流程
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
TQID: 'https://experienceleague.adobe.com/n0zqbcuPD2lvtgYNtdQx5VsBl-FrmzfqU-z2iIn83hg'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: b99602d0-836e-4dbb-979f-c0dec53f883c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 59%

---

# 隱私權工作流程

此工作流程概述的必要步驟，可讓您的 Adobe Analytics 實作準備好支援資料主體的資料隱私權存取和刪除權限。

1. 從 Adobe Experience Platform 中的 [Privacy Service 概觀](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant)頁面開始，了解在為 Analytics 資料加標籤之前要問哪些問題。
1. **設定您的資料保留原則。** Adobe需要資料保留政策才能服務資料隱私權資料存取/刪除請求。  如需詳細資訊，請參閱[資料保留常見問題集](/help/technotes/data-retention.md)。 為了使用 Privacy Service API，您必須確保在 Adobe Analytics 中設定資料保留期。
1. **熟悉資料隱私權標籤、Adobe Analytics ID和名稱空間。** 請參閱[Analytics變數的資料隱私標籤](/help/admin/tools/privacy-labeling/labels.md)和[標籤最佳做法](/help/admin/tools/privacy-labeling/best-practices.md)。
1. **將身分、敏感程度以及資料控管標籤，指派給報表套裝中的每個變數。** 每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須仔細檢視標籤。 啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。 重新實作行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。 請參閱[賦予報告套裝資料標籤](/help/admin/tools/privacy-labeling/namespaces.md)。
1. **連線至Adobe資料隱私權API並提交存取與刪除請求。** Adobe Analytics客戶可以透過呼叫[Adobe Experience Privacy Service API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=zh-Hant)來提交個別資料隱私請求，以存取及刪除客戶資料。 您可以在要求中提交任何 Analytics 識別碼 (如[標籤最佳做法](/help/admin/tools/privacy-labeling/best-practices.md)一節中所述)，連同其各自的命名空間 ID (資料來源 ID)。
1. **檢視及管理您的報表套裝資料隱私權設定。** 檢視[檢視報表套裝的資料控管設定](/help/admin/tools/privacy-labeling/view-settings.md)。
