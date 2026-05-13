---
description: 設定 Experience Cloud 對應的報表套裝，以供 Advertising Analytics 使用。
title: 啟用 Advertising Analytics 的報表套裝
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
TQID: https://experienceleague.adobe.com/sGEXiz2RiDhf9p-2df76o-XxBERTKPB-O-rZeIb4BBI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 27%

---

# 啟用 Advertising Analytics 的報表套裝

若要在Analytics中檢視任何Advertising Analytics搜尋資料，您需要為Advertising Analytics報表設定每個Experience Cloud對應的報表套裝。

1. 導覽至「**[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]**」。

1. 選取已對應至您 Experience Cloud 組織的報表套裝。
1. 按一下 **[!UICONTROL 編輯設定]** > **[!UICONTROL Advertising Analytics 設定]**。

   ![報表](assets/aa-reporting.png)

1. 選取&#x200B;**[!UICONTROL 不熟悉Advertising Analytics？ 按一下這裡以深入瞭解]**，瞭解有關Advertising Analytics的詳細資訊。

1. 設定您希望AMO ID變數使用的變數配置和到期日。 轉換變數(eVar)可讓Adobe Analytics將成功事件歸因於特定變數值。 有時，變數在點選成功事件之前會遇到多個值。 對於這些情況，配置會決定哪個變數值會獲得事件的評分。

   | 設定 | 定義 |
   |--- |--- |
   | **[!UICONTROL 配置]** | 選取範圍： <br/> **[!UICONTROL 原始值（第一個）]**：看到的第一個值會獲得完整配置評分，無論該變數的後續值為何。 <br/>**[!UICONTROL 最近（上一個）]**：最後看到的值會獲得成功事件的完整配置評分，無論之前觸發了哪些變數。 |
   | **[!UICONTROL 有效期限]** | 可讓您指定時段或事件，經過此時段或事件後，eVar值就會過期（即不再接收成功事件的評分）。  如果成功事件發生在 eVar 過期後，「無」值會接收事件的評分 (沒有作用中的 eVar 值)。 |

1. 按一下&#x200B;**[!UICONTROL 啟用Advertising Analytics報告]** （第一次），或&#x200B;**[!UICONTROL 更新Advertising Analytics報告]** （後續時間）。 您的報表套裝現在已準備好接收Advertising Analytics搜尋資料。 您現在已準備好[建立Advertising帳戶](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md)。
