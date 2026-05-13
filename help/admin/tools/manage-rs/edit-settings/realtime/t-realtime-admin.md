---
description: 設定即時報表的管理步驟。
title: 即時報表設定
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
TQID: https://experienceleague.adobe.com/HTu1UvUUIGK0SzAQWEFBclV-P1JaPCJUp6j5MiYC3A0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 68%

---

# 即時報表設定

設定即時報表的管理步驟。

在Adobe Analytics中設定即時報表，包括選取報表套裝，以及為其選取最多3個報表。 依預設，所有使用者都能存取即時報告。

1. 選取您要啟用即時報告的報表套裝。

   導覽至&#x200B;**[!UICONTROL Analytics]** > **[!UICONTROL 管理員>報表套裝]**。

1. 按一下&#x200B;**[!UICONTROL 編輯設定]** > **[!UICONTROL 即時]**。

1. 設定最多 3 個報告的即時資料收集，每個報告各一個量度和三個維度或分類。

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/real_time_admin.png)

   如需深入瞭解支援的即時量度和維度，請參閱[支援的量度和維度](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md)。

   如果您已定義分類，則會以縮排顯示在其所定義的維度下方：

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >針對單一即時報表，目前不支援啟用重複維度，即使為每個維度選取了不同的分類亦同。

   >[!NOTE]
   >
   >在「即時」中，有些維度 (如「搜尋關鍵字」或「產品」) 不會像在 Adobe Analytics 中的其他位置一樣持續存在。 選取非持續性的量度時，會出現此警告：

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

   初次設定報表後，最多可能需要20分鐘資料才能開始串流。 從那時起，資料立即可用。

1. 若要檢視即時報表，請導覽至：

   **[!UICONTROL Workspace]** > **[!UICONTROL 報表]** > **[!UICONTROL 參與]** > **[!UICONTROL 即時]**。

