---
description: 如何以 Enterprise 或 Federated ID 將 Analytics 使用者帳戶移轉至 Adobe Admin Console。
title: 移轉 Enterprise ID 與 Federated ID 的 Analytics 使用者帳戶
feature: Admin Tools
exl-id: 988ed685-4eca-4b0b-a653-9c6a156852f1
role: Admin
TQID: 'https://experienceleague.adobe.com/nJxjJ3au-JRVBAmW4AmCKZtJi7SYS2EWE3roDWFg-L0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 769
ht-degree: 72%

---

# 移轉 Enterprise ID 與 Federated ID 的 Analytics 使用者帳戶

如何以 Enterprise 或 Federated ID 將 Analytics 使用者帳戶移轉至 Adobe Admin Console。

## 先決條件 {#prereqs}

透過 Adobe Admin Console 管理使用者的必備條件。

如需新網域和目錄，請依照以下步驟操作：

* 設定目錄
* 設定網域
* 將網域連結至目錄

如需說明，請參閱[設定識別系統](https://helpx.adobe.com/tw/enterprise/using/set-up-identity.html)。

如果目錄已由其他業務單位或團隊在另一個組織中建立，請按照[目錄託管](https://helpx.adobe.com/tw/enterprise/using/set-up-identity.html#Directorytrusting)中的步驟來在用於Analytics的組織中建立目錄。

## 移轉 Enterprise ID 與 Federated ID 的使用者帳戶 {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

此程序中，您需要完成以下步驟：

* 從&#x200B;**[!UICONTROL Analytics]** > **[!UICONTROL Analytics使用者與Assets]**&#x200B;下載使用者登入清單。

* 從&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL 使用者]**&#x200B;下載目前的使用者清單。

* 比較兩份清單 (尋找重複項目，以免覆寫 Adobe Admin Console 中的帳戶資料)。
* 將含有 Enterprise ID 或 Federated ID 使用者的已完成 [!DNL .csv] (位於&#x200B;**[!UICONTROL 「Admin Console]** > **[!UICONTROL 使用者」]**) 上傳到 Adobe Admin Console。

如果您需要將現有的Adobe ID使用者帳戶移轉至Enterprise ID或Federated ID，請聯絡Adobe客戶服務並請求[大量使用者身分識別引數](https://helpx.adobe.com/tw/enterprise/using/bulk-operations.html)。

**移轉使用者帳戶**

1. 使用下列其中一種方法 (視您是否已移轉使用者而定)，從 Analytics「使用者管理」下載 Analytics 使用者登入檔案 ([!DNL User Logins List.tab])。
   1. *開始移轉之前，*&#x200B;請瀏覽至&#x200B;**[!UICONTROL 「管理員]** > **[!UICONTROL 使用者管理 (舊版)]** > **[!UICONTROL 編輯使用者」]**，按一下&#x200B;**[!UICONTROL 「下載報表」]**。

      ![](/help/admin/tools/user-management/user-migration/assets/download-report.png)

      唯有尚未移轉使用者的客戶，才能在畫面上看見「下載報表」連結。

   1. *如果您已移轉使用者，*&#x200B;請瀏覽至&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL Analytics 使用者與資產」]**。

      ![步驟資訊](/help/admin/tools/user-management/user-migration/assets/admin-analytics-users-assets.png)

   1. 在 [!DNL Users] 頁面中選取使用者，然後按一下&#x200B;**[!UICONTROL 「匯出至 CSV」]**。

      ![步驟資訊](/help/admin/tools/user-management/user-migration/assets/export-csv-migrate.png)

   1. 以 Excel 開啟已下載的 [!DNL User List.csv] 檔案。

      準備將 *`Email`*、*`First Name`* 和 *`Last Name`* 等值複製到 [!DNL sample.csv] 檔案 (下個步驟會加以說明)。

      >[!IMPORTANT]
      >
      >CSV 檔案中的值必須以逗號分隔。

      >[!TIP]
      >
      >在此步驟中，Adobe 建議您簡化使用者清單，以確保 Enterprise ID 或 Federated ID 移轉作業中加入的都是具有有效電子郵件 ID 的使用者。

1. 在 [!UICONTROL Admin Console] 中，下載 Admin Console 使用者清單：

   1. 前往[!UICONTROL 「Admin Console] > **[!UICONTROL 使用者」]**，然後按一下[「將使用者清單匯出為 CSV」](https://helpx.adobe.com/tw/enterprise/using/users.html)。

      ![](/help/admin/tools/user-management/user-migration/assets/export-csv.png)

   1. 比較這兩個檔案：匯出的 [!DNL .csv] 檔案 (此範例中為 [!DNL sample.csv]) 中的現有 Adobe AdobeAdmin Console 使用者，以及 Analytics [!DNL User Logins List.csv] 檔案中的使用者。

      >[!IMPORTANT]
      >
      >如果發現重複項目，請刪除 Analytics [!DNL User Logins List.csv] 檔案中的重複項目。 此步驟有助於防止覆寫Adobe Admin Console中的現有CX Enterprise使用者許可權，並提供您要移轉的帳戶清單。

1. 從 Adobe Admin Console 下載 CSV 範本：
   1. 在「使用者」索引標籤中，按一下&#x200B;**[!UICONTROL 「透過 CSV 新增使用者」]**，然後按一下&#x200B;**[!UICONTROL 「下載 CSV 範本」]**。

      ![步驟資訊](/help/admin/tools/user-management/user-migration/assets/add-users-csv.png)

   1. 選擇&#x200B;**[!UICONTROL 「標準範本」]**。

      如此即可下載 [!DNL sample.csv] 範本檔案。

      ![](/help/admin/tools/user-management/user-migration/assets/download-csv-template.png)

1. 將 *`Email`*、*`First Name`* 和 *`Last Name`* 欄的值從 [!DNL User Logins List.tab] 複製到 [!DNL sample.csv] 範本中對應的欄。

   **範本檔案範例**

   ![](/help/admin/tools/user-management/user-migration/assets/sample.png)

1. 在範本 ([!DNL sample.csv]) 中，完成下列必填欄位：

<table id="table_1B5EEFDB5BD8436EB760BE5FFAB1CF02"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>電子郵件 </p> </td> 
   <td colname="col2"> <p>從 <span class="filepath">User Logins List.tab</span> 中複製。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「名字」 </p> </td> 
   <td colname="col2"> <p>從 <span class="filepath">User Logins List.tab</span> 中複製。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「姓氏」 </p> </td> 
   <td colname="col2"> <p>從 <span class="filepath">User Logins List.tab</span> 中複製。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>身分識別類型 </p> </td> 
   <td colname="col2"> <p><span class="term">Federated ID</span> 或 <span class="term">Enterprise ID</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網域 </p> </td> 
   <td colname="col2"> <p>確定<span class="term">網域</span>和<span class="term">電子郵件</span>資料行中的網域符合先決條件</a>中建立的網域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>國家/地區代碼 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

如需 [!DNL .csv] 檔案中欄位的詳細資訊，請參閱 [CSV 檔案格式](https://helpx.adobe.com/tw/enterprise/using/users.html)。

>[!NOTE]
>
>[!UICONTROL 產品設定]和[!UICONTROL 管理員角色]等其他欄皆可空白。

1. 在 Adobe Admin Console 的「使用者」標籤中，按一下&#x200B;**[!UICONTROL 「透過 CSV 新增使用者」]**&#x200B;上傳範本檔案 (如步驟 3 所示)。
1. 在 Analytics 中，執行移轉工具 (如[移轉 Analytics 使用者帳戶](/help/admin/tools/user-management/user-migration/t-migrate-users.md)所述)。
1. 按一下&#x200B;**[!UICONTROL 「移轉]** > **[!UICONTROL 以 Enterprise ID 移轉」]**。

   ![步驟資訊](/help/admin/tools/user-management/user-migration/assets/migrate-as-enterprise.png)

   在您按下&#x200B;**[!UICONTROL 「移轉」]**&#x200B;後，使用者就會在 Adobe Admin Console 中與 Enterprise ID/Federated ID 帳戶連結。 Analytics舊版使用者帳戶的許可權會符合&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL Analytics]** > **[!UICONTROL 產品設定檔]**&#x200B;中授予Enterprise/Federated ID登入的許可權。 使用者 ID 會顯示在「完成移轉程序」區塊中。 您可以停用其舊版 [!DNL my.omniture.com] 存取權。

   使用者移轉後，「移轉狀態」欄下方的狀態會從&#x200B;**[!UICONTROL 「未啟動」]**&#x200B;變更為&#x200B;**[!UICONTROL 「已移轉」]**。

   在此過程中，移轉工具中顯示的Adobe ID使用者也可以進行移轉。 使用者仍須使用Adobe ID登入，直到執行身分切換為止。 請聯絡Adobe客戶服務，協助處理身分識別切換。
