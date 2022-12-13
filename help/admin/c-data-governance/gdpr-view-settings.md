---
description: 「管理工具」中的資料控管對話方塊提供概述，讓您瞭解已針對資料控管設定哪些報表套裝、是否已對應至 Experience Cloud 組織，以及此報表套裝是否已制定資料保留政策。
title: 檢視/管理報表套裝資料控管設定
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: 196e7672026a284591c0dba2336cb11fc3661c72
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 100%

---

# 檢視/管理報表套裝資料控管設定

「管理工具」中的資料控管對話方塊提供概述，讓您瞭解已針對資料控管設定哪些報表套裝、是否已對應至 Experience Cloud 組織，以及此報表套裝是否已制定資料保留政策。

1. 登入 Adobe Experience Cloud。
1. 導覽至&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理]** > **[!UICONTROL 資料控管」]**。

>[!NOTE]
>
>如果您沒有看到此選單項目，則需要將您新增到具有此功能權限的 [Admin Console 的產品設定檔](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=zh-Hant)。

1. 查看屬於您的登入公司的所有報表套裝：

   ![](assets/privacy_setup_an.png)

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 報表套裝]** | 第一行列出報表套裝的易記名稱。第二行含有報表套裝的內部名稱。如果您可以設定報表套裝的標籤，第一行便會是帶您前往標籤頁面的可點擊連結。 |
| **[!UICONTROL 組織對應]** | <ul><li>已對應：此報表套裝與您目前登入的 Analytics 登入公司已對應至同一個 Experience Cloud 組織。只有套用此設定的報表套裝才能加上標籤。</li><li>已對應至其他組織：其他 Experience Cloud 組織已將此報表套裝套用至其組織。</li></ul> |
| **[!UICONTROL 資料保留政策]** | Analytics 資料隱私權實施作業需要您制定資料保留政策。此設定會顯示：<ul><li>是否已針對此報表套裝制定資料保留政策。</li><li>刪除資料之前 Adobe 要保留資料的時間。預設的資料保留時間為 25 個月。</li></ul>**附註**：若未設定資料保留時間，Adobe Analytics 就無法協助您處理資料隱私權 API 的相關請求，亦即無法處理一般使用者所提出的存取或刪除請求。請聯絡客戶成功案例經理，以設定資料保留時間。 |
| **[!UICONTROL 群組]** | 目前尚未執行分組功能。 |
| 左側側邊列 | 按一下漏斗圖示即可開啟或關閉側邊列。「[!UICONTROL 組織對應]」區段會顯示上述每個類別中的報表套裝數目。「[!UICONTROL 資料保留原則]」區段會顯示貴組織目前制定的每一項資料保留原則，以及指派至該保留原則的報表套裝數目。 |
| **[!UICONTROL 匯出至 CSV]** | 如果您勾選一個或多個報表套裝旁的核取方塊，「匯出至 CSV」選項便會隨即出現。這個選項可讓您下載 CSV 檔案，檔案會包含所有選取報表套裝中所有變數的全部目前標籤定義。我們建議您與法律團隊商議標籤選擇，而這個選項有助於簡化該審核程序。您可以將 .CSV 檔案分享給他們，而不必在登入資料控管 UI 的情況下執行審核程序。 |

{style=&quot;table-layout:auto&quot;}
