---
description: 在Adobe Admin Console中管理Analytics使用者、群組和產品。
subtopic: Users and groups
title: 使用者和產品管理
feature: Admin Tools
exl-id: c0fbbb3a-0011-49d2-89a2-70fce11e0fb2
source-git-commit: beef45403f3c3eb7ac423ca8e0b6db0143ff1b9b
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 74%

---

# 使用者和產品管理

在Adobe Admin Console中管理Analytics使用者、群組和產品。

>[!IMPORTANT]
>
>使用者和產品管理功能已移至 [Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html)。 輪到您遷移使用者時，Adobe 會通知您。

## Adobe Admin Console管理員的說明資源 {#section_C13BBB89E4F248F193358BB3A59DD502}

| 工作或資源 | 說明 |
| --- | --- |
| 將 Analytics 使用者 ID 遷移到 Adobe Admin Console | Adobe 會協助 Analytics 管理員將使用者 ID 移轉至 Adobe Admin Console。此移轉作業會分批進行。輪到移轉您的使用者時，Adobe 會以含有相關說明的電子郵件通知 Analytics 管理員。[Analytics User Management](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html?lang=zh-Hant) 中有遷移工具可簡化這項作業。<p>**重要**:使用者移轉當天，您先前的權限群組會自動複製到Adobe Admin Console。 您再也無法於 Analytics「管理工具」中邀請新的使用者或建立新群組。 如需如何準備遷移作業以及受影響之管理功能的相關資訊，請檢閱 Analytics 使用者遷移至 Adobe Admin Console 的常見問答和說明。 |
| 啟動 Adobe Admin Console | 使用者帳戶移轉後，您就可以在Adobe Admin Console中管理所有解決方案的使用者和產品。 瀏覽至：`https://adminconsole.adobe.com/enterprise/`。 也請參閱[管理 Experience Cloud 使用者和產品](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=zh-Hant)。 |
| 管理 Adobe Analytics 產品描述檔、使用者和權限 | 請參閱 [Adobe Admin Console 中的 Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=zh-Hant)。 |

<!---
## User Management Descriptions {#section_7C19842A3D4249109A9399D4DF18DE75}

The following table describes elements on the [!UICONTROL Users] tab in [!UICONTROL User Management].

<table id="table_6F81D1095EB945D8995FF971B65BA52A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins available</span> </td> 
   <td colname="col2"> The maximum number of user accounts you can create for this company. If necessary, you can contact your Account Representative or Customer Care to increase this number at no charge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins in use</span> </td> 
   <td colname="col2"> The number of user accounts currently in use for this company. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins Remaining</span> </td> 
   <td colname="col2"> The difference between the user account maximum and the number of existing user accounts. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Add New User</span> </td> 
   <td colname="col2"> <p>Lets you add a user account to the company. This link is available only if the Number of User Logins Remaining is greater than 0. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Download Report</span> </td> 
   <td colname="col2">Exports the contents of the <span class="wintitle"> Users</span> table to a tab-delimited file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Login</span> </td> 
   <td colname="col2"> <p>The user name. You can click the user name to edit the user account properties. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> First Name</span> </td> 
   <td colname="col2"> The user's first (given) name. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Name</span> </td> 
   <td colname="col2"> The user's surname (family name). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Title</span> </td> 
   <td colname="col2"> The user's job title. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Admin</span> </td> 
   <td colname="col2"> Specifies if the user account has administrative privileges. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Login</span> </td> 
   <td colname="col2"> Displays a timestamp of the last login for this user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Create Time</span> </td> 
   <td colname="col2"> Shows the date and time when the login account was created. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Expires</span> </td> 
   <td colname="col2"> Displays the account expiration account, if applicable. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Manage</span> </td> 
   <td colname="col2"> Provides links for user account management. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Edit</span> </td> 
   <td colname="col2"> <p>Edit user account settings. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Delete</span> </td> 
   <td colname="col2"> Delete the user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Transfer</span> </td> 
   <td colname="col2">Assign the privileges (permissions and resource access) of one user account to another. <p>See <a href="/help/admin/user-management2/c-user-management/t-transfer-user-accout-privileges.md"> Transfer user account privileges</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Login as this user</span> </td> 
   <td colname="col2"> <p>Allows admins to impersonate and log in as a non-admin account. Admin accounts cannot be impersonated. </p> </td> 
  </tr> 
 </tbody> 
</table>
-->