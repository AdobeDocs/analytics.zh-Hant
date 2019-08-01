---
description: 瞭解如何為 Analytics 使用者停用舊版登入。
seo-description: 瞭解如何為 Analytics 使用者停用舊版登入。
seo-title: 停用舊版登入
title: 停用舊版登入
uuid: 085874b2-10bb-4a56-a337-f3104428 d71 e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# 停用舊版登入{#disable-legacy-logins}

瞭解如何為 Analytics 使用者停用舊版登入。

將使用者從舊版 Analytics 使用者管理系統移轉至 Adobe Admin Console 後，即可停用他們的舊版登入功能。停用舊版登入後，如果使用者嘗試使用舊版登入，系統會將使用者重新導向到 Experience Cloud 登入。

1. Open the Migration tool in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User ID Migration]**.
1. In the [!DNL User Information] section, locate the domain containing the users you want to work with, then click **[!UICONTROL Select Users]**.
1. 選取具有您要停用之舊版登入的使用者。

   ![](assets/user-info.png)

   The users that are eligible will have a status of *`Migrated`* under the Migration Status column. 您必須先移轉使用者，才能停用其舊版登入。
1. Click **[!UICONTROL Disable Legacy Login]**, then click **[!UICONTROL Done]**.

   「停用舊版登入」表示使用者可以繼續使用其舊版 [!DNL my.omniture.com] 使用者名稱和密碼。

   您無法為尚未移轉的使用者停用舊版登入功能。一旦停用，使用者必須使用其 Experience Cloud ID 登入和存取 Analytics。

