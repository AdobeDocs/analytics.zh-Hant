---
description: 說明管理員如何為一組使用者啟用 Data Warehouse 報告存取權的步驟。
title: 新增 Data Warehouse 使用者群組
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 新增 Data Warehouse 使用者群組

說明管理員如何為一組使用者啟用 Data Warehouse 報告存取權的步驟。

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. 按一下 **[!UICONTROL Edit Groups]**.
1. 按一下 **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. 提供下列群組資訊:

   例如, `Data Warehouse Access`.
1. 在欄位中輸入說 **[!UICONTROL Group Description]** 明。
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. 在下 [!UICONTROL Tools]面，啟用 **[!UICONTROL All Tools]**。

   或者，按一 **[!UICONTROL Customize]**&#x200B;下，然後啟 **[!UICONTROL Custom Data Warehouse Report]**&#x200B;用。

1. 在下 [!UICONTROL Assign User Logins]方，新增所要的使用者登入。
1. 按一下 **[!UICONTROL Save Group]**.

   新增至此群組的使用者下次登入時，就會看到 Data Warehouse 選項已新增至[!UICONTROL Reports & Analytics]「」功能表。

   >[!NOTE]
   >
   >萬一發生權限衝突 (例如一位使用者被指派給兩個群組，其中一個拒絕存取某項功能，但另一個授予該功能的存取權)，則系統會限制權限。屬於拒絕 Data Warehouse 存取之群組的使用者，可能需從該群組中移除。

>[!MORELIKETHIS]
>
>* [群組 ](/help/admin/user-management2/c-user-groups/groups.md)

