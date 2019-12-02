---
description: 'null'
title: 隱私權工作流程
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: ht
source-git-commit: dcb07f8717337da904b252864eb7f800f1728231

---


# 隱私權工作流程

此工作流程概述的必要步驟，可讓您的 Adobe Analytics 實作準備好支援資料主體的資料隱私權存取和刪除權限。

| 工作說明 | 指示與更多資訊的連結 |
|--- |--- |
| **步驟 1**: 確認所有可能包含資料隱私權相關資料的報表套裝均已對應至您的 Experience Cloud (或 IMS) 組織。資料隱私權請求已使用 Experience Cloud 組織提交，並套用至該組織申請的所有報表套裝。即使未對應至該組織的報表套裝是登入公司的一部分，請求也不會套用到這些報表套裝。 | 請參閱[將報表套裝對應至組織](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/about-core-services/report-suite-mapping.html)。 |
| **步驟 2**: 設定您的資料保留政策。 | 需要制定資料保留政策，Adobe 才能為資料隱私權資料存取/刪除請求提供服務。如需更多詳細資訊，請參閱這篇 [Analytics 資料保留常見問題集](/help/technotes/data-retention.md)。 |
| **步驟 3**: 熟悉 DULE/資料隱私權標籤、Adobe Analytics ID、命名空間及 ID 擴增。 | 請閱讀此文件集中的這些主題:<ul><li>[Analytics 變數的資料隱私權標籤](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[標籤最佳作法](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **步驟 4**: 將身分、敏感程度以及資料控管標籤，指派給報表套裝中的每個變數。注意: 請記住，每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須檢閱標籤。啟用新解決方案整合時也必須檢閱標籤，因為它們可能會公開需要加上標籤的新變數。重新實作行動應用程式或網站可能會改變現有變數的使用方式，因此也可能需要更新標籤。 | 請依照[標籤報表套裝資料](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)的指示操作。 |
| **步驟 5**: 連線至 Adobe 資料隱私權 API 並提交存取與刪除請求。 | Adobe Analytics 客戶可以透過呼叫 [Adobe Experience Cloud 資料隱私權 API](https://www.adobe.io/apis/experienceplatform/gdpr.html) 來提交個別資料隱私權請求，以便存取及刪除客戶資料。您可以提交任何 Analytics 識別碼 (如[標籤最佳實務](/help/admin/c-data-governance/gdpr-analytics-ids.md)一節中所述)，及其各自的命名空間 ID (資料來源 ID)。 |
| **步驟 6**: 檢視及管理您的報表套裝資料隱私權設定。 | 請依照[檢視報表套裝資料控管設定](/help/admin/c-data-governance/gdpr-view-settings.md)的指示操作。 |
