---
description: 設定 Experience Cloud 對應的報表套裝，以供 Advertising Analytics 使用。
title: 啟用 Advertising Analytics 的報表套裝
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 47%

---

# 啟用 Advertising Analytics 的報表套裝

若要在Analytics中檢視任何Advertising Analytics搜尋資料，您需要為Advertising Analytics報表設定每個Experience Cloud對應的報表套裝。

1. 導覽至「**[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]**」。

1. 選取已對應至您 Experience Cloud 組織的報表套裝。
1. 按一下 **[!UICONTROL 編輯設定]** > **[!UICONTROL Advertising Analytics 設定]**。

   ![報表](assets/aa-reporting.png)

   >[!IMPORTANT]
   >
   >AMO ID指的是要插入搜尋資料的Adobe Advertising Cloud (也稱為Adobe Media Optimizer)變數。

1. 選取&#x200B;**[!UICONTROL 不熟悉Advertising Analytics？ 按一下這裡以深入瞭解]**，瞭解有關Advertising Analytics的詳細資訊。

1. 設定您希望AMO ID變數使用的變數配置和到期日。 轉換變數 (eVars) 可讓 Adobe Analytics 將成功事件歸因於特定變數值。有時候，變數在感應到成功事件之前會遇到一個以上的值。在此情況下，配置會決定哪個變數值可以取得該事件的評分。

   | 設定 | 定義 |
   |--- |--- |
   | **[!UICONTROL 配置]** | 選取範圍： <br/> **[!UICONTROL 原始值（第一個）]**：看到的第一個值會獲得完整配置評分，無論該變數的後續值為何。 <br/>**[!UICONTROL 最近（上一個）]**：最後看到的值會獲得成功事件的完整配置評分，無論之前觸發了哪些變數。 |
   | **[!UICONTROL 有效期限]** | 可讓您指定時段或事件，在發生此時段或事件後，eVar值就會過期（即不再接收成功事件的評分）。  如果成功事件發生在 eVar 過期後，「無」值會接收事件的評分 (沒有作用中的 eVar 值)。 |

1. 按一下&#x200B;**[!UICONTROL 「啟用 Advertising Analytics 報表」]**(首次)，或&#x200B;**[!UICONTROL 「更新 Advertising Analytics 報表」]**(後續)。您的報表套裝現在已準備就緒，可以接收 Advertising Analytics 搜尋資料。您現在已準備好[建立Advertising帳戶](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)。
