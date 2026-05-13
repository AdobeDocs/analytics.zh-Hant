---
description: 設定即時報表的管理步驟。
title: 設定即時報程
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
TQID: https://experienceleague.adobe.com/wmZj-F8P4ectiMUnpy9yYT-pviys2m2aBGAVtP5kNNI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 68%

---

# 設定即時報程

下列資訊包含設定即時報表的管理步驟。

這包括選取報表套裝，以及為其設定最多3個報表。

1. 選取您要啟用即時報告的報表套裝。

   1. 在Analysis Workspace中，選取&#x200B;[!UICONTROL **Workspace**]&#x200B;索引標籤，然後選取&#x200B;[!UICONTROL **報表**] > [!UICONTROL **參與**] > **[!UICONTROL 即時]**。

   1. 從上方的下拉式清單中選取報表套裝：

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report_suite_selector.png)

      如果您嘗試對尚未設定即時報表的報表套裝檢視即時報表，會出現一則訊息，供您設定報表套裝。

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/rep_suite_not_set_up.png)

1. 選取&#x200B;**[!UICONTROL 設定]**&#x200B;以執行[!UICONTROL 報表套裝管理員]。

   (也可從&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員 > 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 即時」]**&#x200B;中存取。)

1. 開啟&#x200B;**[!UICONTROL 啟用即時]**&#x200B;設定。
1. 設定最多 3 個報告的即時資料收集，每個報告各一個量度和三個維度或分類。

   ![](assets/real_time_admin.png)

   如需深入瞭解支援的即時量度和維度，請參閱[支援的量度和維度](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md)。

   如果您已定義分類，則會以縮排顯示在其所定義的維度下方：

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >針對單一即時報表，目前不支援啟用重複維度，即使為每個維度選取了不同的分類亦同。

   >[!NOTE]
   >
   >在「即時」中，有些維度 (如「搜尋關鍵字」或「產品」) 不會像在 Adobe Analytics 中的其他位置一樣持續存在。 選取非持續性的量度時，會出現此警告：

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;或&#x200B;**[!UICONTROL 儲存並檢視報表]**。

   初次設定報表後，最多可能需要20分鐘資料才能開始串流。 從那時起，資料立即可用。

1. 依預設，所有使用者都能存取即時報告。
