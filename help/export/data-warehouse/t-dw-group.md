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

1. 按一下&#x200B;**[!UICONTROL 「Analytics]** &gt; **[!UICONTROL 管理員]** &gt; **[!UICONTROL 使用者管理」]**。
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. 提供下列群組資訊:

   例如, `Data Warehouse Access`.
1. Type a description in the **[!UICONTROL Group Description]** field.
1. 在&#x200B;**報表套裝存取**&#x200B;區段中，選取您要讓群組成員有權存取的報表套裝.
1. Under [!UICONTROL Tools], enable **[!UICONTROL All Tools]**.

   Alternatively, click **[!UICONTROL Customize]**, then enable **[!UICONTROL Custom Data Warehouse Report]**.

1. 在「[!UICONTROL 指定使用者登入]」下方，新增所需的使用者登入。
1. 按一下&#x200B;**[!UICONTROL 「儲存群組」]**。

   新增至此群組的使用者下次登入時，就會看到 Data Warehouse 選項已新增至[!UICONTROL 「Reports &amp; Analytics」]功能表。

   >[!NOTE]
   >
   >如果權限發生衝突（例如指派給兩個群組的使用者，其中一個拒絕存取某個功能，另一個授予相同存取權），系統會限制權限。 屬於拒絕 Data Warehouse 存取之群組的使用者，可能需從該群組中移除。

>[!MORELIKETHIS]
>
>* [群組 ](/help/admin/user-management2/c-user-groups/groups.md)

