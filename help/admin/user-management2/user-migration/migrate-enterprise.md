---
description: 如何以 Enterprise 或 Federated ID 將 Analytics 使用者帳戶移轉至 Admin Console。
title: 移轉 Enterprise 與 Federated ID 的 Analytics 使用者帳戶
uuid: f90bf78a-5603-4bef-b714-13215301187c
translation-type: tm+mt
source-git-commit: 3db8481434f3db43732f0b54a58c6d4a29bce652

---


# 移轉 Enterprise 與 Federated ID 的 Analytics 使用者帳戶{#migrate-analytics-user-accounts-for-enterprise-and-federated-ids}

如何以 Enterprise 或 Federated ID 將 Analytics 使用者帳戶移轉至 Admin Console。

## 必備條件 {#prereqs}

透過 Admin Console 管理使用者的必備條件。

如需新網域和目錄，請依照以下步驟操作:

* 設定目錄
* 設定網域
* 將網域連結至目錄

如需說明，請參閱[設定身分系統](https://helpx.adobe.com/enterprise/using/set-up-identity.html)。

如果其他組織已有另一個業務單位或團隊建立目錄，請依照[目錄信任](https://helpx.adobe.com/enterprise/using/set-up-identity.html#Directorytrusting)所述步驟，在您預計由 Analytics 使用的組織中建立目錄。

## 移轉 Enterprise 與 Federated ID 的 使用者帳戶 {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

此程序中，您需要完成以下步驟:

* 從&#x200B;**[!UICONTROL 「Analytics]** &gt; **[!UICONTROL Analytics 使用者與資產」]**&#x200B;下載使用者登入清單。

* 從&#x200B;**[!UICONTROL 「Admin Console]** &gt; **[!UICONTROL 使用者」]**&#x200B;下載最新使用者清單。

* 比較兩份清單 (尋找重複項目，以免覆寫 Admin Console 中的帳戶資料)。
* 將含有 Enterprise ID 或 Federated ID 使用者的已完成 [!DNL .csv] (位於&#x200B;**[!UICONTROL 「Admin Console]** &gt; **[!UICONTROL 使用者」]**) 上傳到 Admin Console。

如果您需要將現有的 Adobe ID 使用者帳戶移轉到 Enterprise ID 或 Federated ID，請聯絡 Adobe 客戶服務並提出[大量使用者身分切換](https://helpx.adobe.com/enterprise/using/bulk-operations.html)申請。

**移轉使用者帳戶**

1. 使用下列其中一種方法 (視您是否已移轉使用者而定)，從 Analytics「使用者管理」下載 Analytics 使用者登入檔案 ([!DNL User Logins List.tab])。
   1. *開始移轉之前，*&#x200B;請前往&#x200B;**[!UICONTROL 「管理員]** &gt; **[!UICONTROL 使用者管理 (舊版)]** &gt; **[!UICONTROL 編輯使用者」]**，按一下&#x200B;**[!UICONTROL 「下載報表」]**。

      ![](assets/download-report.png)

      唯有尚未移轉使用者的客戶，才能在畫面上看見「下載報表」連結。

   1. *如果您已移轉使用者，*&#x200B;請前往&#x200B;**[!UICONTROL 「Analytics]** &gt; **[!UICONTROL Analytics 使用者與資產」]**。

      ![步驟資訊](assets/admin-analytics-users-assets.png)

   1. 在 [!DNL Users] 頁面中選取使用者，然後按一下&#x200B;**[!UICONTROL 「匯出至 CSV」]**。

      ![步驟資訊](assets/export-csv-migrate.png)

   1. 以 Excel 開啟已下載的 [!DNL User List.csv] 檔案。

      準備將 *`Email`*、*`First Name`* 和 *`Last Name`* 值複製到 [!DNL sample.csv] 檔案 (在下個步驟中說明)。

      > [!IMPORTANT] CSV 檔案中的值必須以逗號分隔。

      > [!TIP] 在此步驟中，建議您簡化使用者清單，確保 Enterprise 或 Federated ID 移轉作業中加入的都是具有有效電子郵件 ID 的使用者。

1. In the [!UICONTROL Admin Console], download a list of Admin Console users:

   1. 前往[!UICONTROL 「Admin Console] &gt; **[!UICONTROL 使用者」]**，然後按一下[「將使用者清單匯出為 CSV」](https://helpx.adobe.com/enterprise/using/users.html)。

      ![](assets/export-csv.png)

   1. 比較這兩個檔案: 匯出的 [!DNL .csv] 檔案 (此範例中為 [!DNL sample.csv]) 中的現有 Admin Console 使用者，以及 Analytics [!DNL User Logins List.csv] 檔案中的使用者。

      > [!IMPORTANT] 如果發現重複項目，請刪除 Analytics [!DNL User Logins List.csv] 檔案中的重複項目。這麼做可防止覆寫 Admin Console 中的現有 Experience Cloud 使用者權限，並提供您要移轉的帳戶清單。

1. 從 Admin Console 下載 CSV 範本:
   1. 在「使用者」標籤中，按一下&#x200B;**[!UICONTROL 「透過 CSV 新增使用者」]**，然後按一下&#x200B;**[!UICONTROL 「下載 CSV 範本」]**。

      ![步驟資訊](assets/add-users-csv.png)

   1. 選擇&#x200B;**[!UICONTROL 「標準範本」]**。

      如此即可下載 [!DNL sample.csv] 範本檔案。

      ![](assets/download-csv-template.png)

1. 將 *`Email`*、*`First Name`* 和 *`Last Name`* 列的值從 [!DNL User Logins List.tab] 複製到 [!DNL sample.csv] 範本中對應的欄。

   **範本檔案範例**

   ![](assets/sample.png)

1. 在範本 ([!DNL sample.csv]) 中，完成下列必填欄位:

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
   <td colname="col1"> <p>身分類型 </p> </td> 
   <td colname="col2"> <p><span class="term">Federated ID</span> 或 <span class="term">Enterprise ID</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網域 </p> </td> 
   <td colname="col2"> <p>確認<span class="term">「網域」</span>和<span class="term">「電子郵件」</span>欄中的網域符合在「先決條件」</a>中建立的網域。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>國家/地區代碼 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

如需 [!DNL .csv] 檔案中欄位的詳細資訊，請參閱 [CSV 檔案格式](https://helpx.adobe.com/enterprise/using/users.html)。

> [!NOTE] 其他欄(例如「產 [!UICONTROL 品設定] 」 [!UICONTROL 和「管理員角色] 」)可以是空白。

1. 在 Admin Console 的「使用者」標籤中，按一下&#x200B;**[!UICONTROL 「透過 CSV 新增使用者」]**&#x200B;上傳範本檔案 (如步驟 3 所示)。
1. 在 Analytics 中，執行移轉工具 (如[移轉 Analytics 使用者帳戶](/help/admin/user-management2/user-migration/t-migrate-users.md)所述)。
1. 按一下&#x200B;**[!UICONTROL 「移轉]** &gt; **[!UICONTROL 以 Enterprise ID 移轉」]**。

   ![步驟資訊](assets/migrate-as-enterprise.png)

   在您按下&#x200B;**[!UICONTROL 「移轉」]**&#x200B;後，使用者就會在 Admin Console 中與 Enterprise ID/Federated ID 帳戶連結。Analytics 的舊版使用者帳戶權限會符合&#x200B;**[!UICONTROL 「Admin Console]** &gt; **[!UICONTROL Analytics]** &gt; **[!UICONTROL 產品描述檔」]**&#x200B;中授予 Enterprise/Federated ID 登入的權限。使用者 ID 會顯示在「完成移轉程序」區塊中。您可以停用其舊版 [!DNL my.omniture.com] 存取權。

   After migrating users, the status under the Migration Status column changes from **[!UICONTROL Not Initiated]** to **[!UICONTROL Migrated]**.

   移轉工具中顯示的 Adobe ID 使用者也可透過此程序移轉。切換身分之前，使用者仍需使用其 Adobe ID 登入。如需身分切換的相關說明，請聯絡 Adobe 客戶服務。
