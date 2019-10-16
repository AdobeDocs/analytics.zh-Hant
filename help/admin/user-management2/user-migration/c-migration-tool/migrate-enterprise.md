---
description: 如何以 Enterprise 或 Federated ID 將 Analytics 使用者帳戶移轉至 Admin Console。
seo-description: 如何以 Enterprise 或 Federated ID 將 Analytics 使用者帳戶移轉至 Admin Console。
seo-title: 移轉 Enterprise 與 Federated ID 的 Analytics 使用者帳戶
title: 移轉 Enterprise 與 Federated ID 的 Analytics 使用者帳戶
uuid: f90bf78a-5603-4bef-b714-13215301187c
translation-type: tm+mt
source-git-commit: 3276298eed17827c92162dd09856bed3f22de468

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

## 移轉 Enterprise 和 Federated ID 的使用者帳戶 {#task-0cfb3e4400fd4ab58e4d9704528b05fa}

此程序中，您需要完成以下步驟:

* Download a user login list from **[!UICONTROL Analytics]** &gt; **[!UICONTROL Analytics Users &amp; Assets]**.

* Download a current users list from the **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Users]**.

* 比較兩份清單 (尋找重複項目，以免覆寫 Admin Console 中的帳戶資料)。
* Upload a finished [!DNL .csv] (from **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Users]**) with Enterprise ID or Federated ID users to the Admin Console.

如果您需要將現有的 Adobe ID 使用者帳戶移轉到 Enterprise ID 或 Federated ID，請聯絡 Adobe 客戶服務並提出[大量使用者身分切換](https://helpx.adobe.com/enterprise/using/bulk-operations.html)申請。

**移轉使用者帳戶**

1. 使用下列其中一種方法 (視您是否已移轉使用者而定)，從 Analytics「使用者管理」下載 Analytics 使用者登入檔案 ([!DNL User Logins List.tab])。
   1. *在移轉之前，導覽至* 「管理員 **** &gt;使用者管 **[!UICONTROL 理（編輯舊版）]** &gt;編輯舊版使用者 ********」，然後按一下「下載報表」。

      ![](assets/download-report.png)

      唯有尚未移轉使用者的客戶，才能在畫面上看見「下載報表」連結。

   1. *如果您已移轉使用者，請導覽* 至「 **[!UICONTROL Analytics]** &gt; **[!UICONTROL Analytics使用者和資產」]**。

      ![步驟資訊](assets/admin-analytics-users-assets.png)

   1. On the [!DNL Users] page, select users, then click **[!UICONTROL Export to CSV]**.

      ![步驟資訊](assets/export-csv-migrate.png)

   1. Open the downloaded [!DNL User List.csv] file in Excel.

      請準備好將、 *`Email`*&#x200B;和值複製 *`First Name`**`Last Name`*[!DNL sample.csv] 到檔案（在下一步中介紹）。

      >[!IMPORTANT]
      >
      >CSV檔案中的值必須以逗號分隔。

      **秘訣**: 此步驟中，建議您簡化使用者清單，以確保 Enterprise 或 Federated ID 移轉作業只會包含具有效電子郵件 ID 的使用者。

1. 在 Admin Console 中，下載 Admin Console 使用者清單:

   1. Navigate to [Admin Console](http://adminconsole.adobe.html/#) &gt; **[!UICONTROL Users]**, then click [Export users list to CSV](https://helpx.adobe.com/enterprise/using/users.html).

      ![](assets/export-csv.png)

   1. Compare the two files: the existing Admin Console users in the exported [!DNL .csv] file ( [!DNL sample.csv], in this example) with the users in the Analytics [!DNL User Logins List.csv] file.

      >[!IMPORTANT]
      >
      >If you find duplicates, delete them from the Analytics [!DNL User Logins List.csv] file. 這麼做可防止覆寫 Admin Console 中的現有 Experience Cloud 使用者權限，並提供您要移轉的帳戶清單。

1. 從 Admin Console 下載 CSV 範本:
   1. On the Users tab, click **[!UICONTROL Add users by CSV]**, then **[!UICONTROL Download CSV Template]**.

      ![步驟資訊](assets/add-users-csv.png)

   1. Choose **[!UICONTROL Standard Template]**.

      如此即可下載 [!DNL sample.csv] 範本檔案。

      ![](assets/download-csv-template.png)

1. 將、 *`Email`*&#x200B;和 *`First Name`*&#x200B;列值從復 *`Last Name`* 制到模板中的對應 [!DNL User Logins List.tab][!DNL sample.csv] 列。

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
   <td colname="col2"> <p><span class="term"> Federated ID</span> 或 <span class="term"> Enterprise ID</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>網域 </p> </td> 
   <td colname="col2"> <p>確認 網 <span class="term"> 域和</span> 「電子郵件 <span class="term"> 」欄會符合必要條件中建立的網</span> 域 <a href="/help/admin/user-management2/user-migration/c-migration-tool/migrate-enterprise.md#prereqs" format="dita" scope="local"></a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>國家/地區代碼 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
 </tbody> 
</table>

For more information about the fields in the [!DNL .csv] file, see [CSV file format](https://helpx.adobe.com/enterprise/using/users.html).

>[!NOTE]
>
>其他欄，例如 *`Product Configurations`* 和 *`Admin Roles`* 可以是空白。

1. On the Users tab in the Admin Console, upload the template file by clicking **[!UICONTROL Add users by CSV]** (as shown in Step 3.).
1. 在Analytics中，執行移轉工具(如移轉 [Analytics使用者帳戶所述](/help/admin/user-management2/user-migration/c-migration-tool/t-migrate-users.md))。
1. Click **[!UICONTROL Migrate]** &gt; **[!UICONTROL Migrate as Enterprise IDs]**.

   ![步驟資訊](assets/migrate-as-enterprise.png)

   When you click **[!UICONTROL Migrate]**, user are linked to the Enterprise ID/Federated ID account in Admin Console. The permissions of the legacy user account in Analytics will match the permissions granted to the Enterprise/Federated ID login in **[!UICONTROL Admin Console]** &gt; **[!UICONTROL Analytics]** &gt; **[!UICONTROL Product Profiles]**. 使用者 ID 會顯示在「完成移轉程序」區塊中。您可以停用其舊版 [!DNL my.omniture.com] 存取權。

   After migrating users, the status under the Migration Status column changes from *`Not Initiated`* to *`Migrated`*.

   移轉工具中顯示的 Adobe ID 使用者也可透過此程序移轉。切換身分之前，使用者仍需使用其 Adobe ID 登入。如需身分切換的相關說明，請聯絡 Adobe 客戶服務。
