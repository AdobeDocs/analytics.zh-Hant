---
description: 瞭解如何停用Analytics使用者的舊版登入。
title: 停用舊版登入
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
role: Admin
TQID: https://experienceleague.adobe.com/xwLXKuaeoKB5-TSVC7FLQXdUsBEeOg-zuITMa8Z3OIo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 185
ht-degree: 52%

---

# 停用舊版登入

瞭解如何停用Analytics使用者的舊版登入。

使用者從舊版Analytics使用者管理系統移轉至Adobe Admin Console後，您就可以停用其舊版登入。 如果停用舊版登入，系統會在使用者嘗試使用舊版登入時，將使用者重新導向至Experience Cloud登入。

1. 在&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理]** > **[!UICONTROL 使用者 ID 移轉」]**&#x200B;中，開啟「移轉」工具。
1. 在 [!DNL User Information] 中找出含有所需使用者的網域，然後按一下&#x200B;**[!UICONTROL 「選取使用者」]**。
1. 選取具有您要停用之舊版登入的使用者。

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

   符合資格的使用者在「移轉狀態」欄下的狀態會變成 *`Migrated`*。 您必須先移轉使用者，才能停用其舊版登入。
1. 按一下&#x200B;**[!UICONTROL 「停用舊版登入」]**，然後按一下&#x200B;**[!UICONTROL 「完成」]**。

   「停用舊版登入」表示使用者可以繼續使用其舊版 [!DNL my.omniture.com] 使用者名稱和密碼。

   您無法停用尚未移轉之使用者的舊版登入。 停用後，使用者必須使用其Experience Cloud ID登入及存取Analytics。
