---
description: 說明將篩選條件套用至流失報表的步驟。
title: 使用請求精靈篩選流失報告
feature: Report Builder
role: User, Admin
exl-id: 6134d7d4-7287-4a83-92b6-d250ca15cf69
TQID: https://experienceleague.adobe.com/b-OBsmKfOFGtPK3Ar6pJtGUc3vZ4L2Jeei2sNK-7Npg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 248
ht-degree: 77%

---

# 使用請求精靈篩選流失報告

{{legacy-arb}}

說明將篩選條件套用至流失報表的步驟。

此範例顯示「頁面流失」報表。

1. 在 Adobe Report Builder 中，按一下&#x200B;**[!UICONTROL 「建立」]**&#x200B;以開啟「請求精靈」。
1. 選擇正確的報表套裝。
1. 在左側的樹狀檢視中，選取&#x200B;**[!UICONTROL 「路徑]** > **[!UICONTROL 頁面]** > **[!UICONTROL 頁面流失」]**。

   ![顯示Report Builder目錄Windows樹狀檢視的熒幕擷圖。 已選取頁面流失。](assets/page_fallout.png)

1. 設定適當的[日期範圍](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 在精靈的步驟 2 中，按一下&#x200B;**[!UICONTROL 「列標籤」]**&#x200B;底下的&#x200B;**[!UICONTROL 「定義查核點」]**&#x200B;連結 (在流失報表中，您永遠必須定義路徑元素，這點與路徑報表已預先套用模式不同)。

   ![顯示[定義查核點]連結的熒幕擷圖。](assets/define_checkpoints.png)

1. 選取&#x200B;**[!UICONTROL 「篩選」]**&#x200B;選項。

1. 在&#x200B;**[!UICONTROL 「定義網站區域流失查核點」]**&#x200B;對話方塊中，從儲存格範圍或清單定義查核點。 接著，按一下&#x200B;**[!UICONTROL 「確定」]**。
1. 決定要從儲存格範圍或清單選取。
1. 如果您要從清單選取，請按一下&#x200B;**[!UICONTROL 「新增」]**，選取要新增至流失路徑的查核點。 您可以定義 3 到 8 個查核點 (按一下&#x200B;**[!UICONTROL 「更多」]**&#x200B;可搜尋可用元素)。

   如需縮小篩選範圍的詳細資訊，請參閱[篩選維度](/help/analyze/legacy-report-builder/layout/c-filter-dimensions/filter-dimensions.md)。

1. 選取&#x200B;**[!UICONTROL 可用元素]**&#x200B;並按一下橘色箭頭，可將其從左欄移至右側。
1. 按三次&#x200B;**[!UICONTROL 「確定」]**，然後按一下&#x200B;**[!UICONTROL 「完成」]**。

   報表應該會立即重新整理。
