---
description: 瞭解如何為 Analytics 使用者停用舊版登入。
title: 停用舊版登入
uuid: 085874b2-10bf-4a56-a337-f3104428d71e
translation-type: tm+mt
source-git-commit: 1ec080acf65c31b077a3daf3846f233f01e011b8

---


# 停用舊版登入{#disable-legacy-logins}

瞭解如何為 Analytics 使用者停用舊版登入。

將使用者從舊版 Analytics 使用者管理系統移轉至 Adobe Admin Console 後，即可停用他們的舊版登入功能。停用舊版登入後，如果使用者嘗試使用舊版登入，系統會將使用者重新導向到 Experience Cloud 登入。

1. 在&#x200B;**[!UICONTROL 「Analytics]** &gt; **[!UICONTROL 管理員]** &gt; **[!UICONTROL 使用者 ID 移轉」]**&#x200B;中，開啟「移轉」工具。
1. 在 [!DNL User Information] 中找出含有所需使用者的網域，然後按一下&#x200B;**[!UICONTROL 「選取使用者」]**。
1. 選取具有您要停用之舊版登入的使用者。

   ![](assets/user-info.png)

   符合資格的使用者在「移轉狀態」欄下的狀態會變成 *`Migrated`*。您必須先移轉使用者，才能停用其舊版登入。
1. 按一下&#x200B;**[!UICONTROL 「停用舊版登入」]**，然後按一下&#x200B;**[!UICONTROL 「完成」]**。

   「停用舊版登入」表示使用者可以繼續使用其舊版 [!DNL my.omniture.com] 使用者名稱和密碼。

   您無法為尚未移轉的使用者停用舊版登入功能。一旦停用，使用者必須使用其 Experience Cloud ID 登入和存取 Analytics。

