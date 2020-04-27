---
description: 套用特定維度字詞的篩選。
title: 特定篩選
topic: Report builder
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 特定篩選

套用特定維度字詞的篩選。

您可以建立與實際條件相符的篩選來搜尋特定維度。例如，您可以建立以下類型的篩選器：[!DNL homepage.htm]、[!DNL contact_us.html]、[!DNL corporate_info.html] 中的頁面。

**建立特定的篩選**

1. 建立或編輯請求，然後前往 [!UICONTROL Request Wizard: Step 2]。

   ![步驟結果](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.

   ![步驟結果](assets/choose_page_specific01.png)

1. Enable **[!UICONTROL Specific]**, then enable one of the following options:

   * **從儲存格範圍：**&#x200B;可讓您選擇儲存格中的資料。您可以選擇︰
   * **範圍內的所有儲存格：**&#x200B;可讓您映射範圍內的每一個儲存格。描述文字會說明您必須選擇的儲存格群組數量。若要映射多個儲存格群組，請在選擇儲存格時按住 Ctrl 鍵。如果必須映射的範圍內只含有一個儲存格，這便是唯一可用的選項。
   * **範圍的第一個儲存格：**&#x200B;您只需要選擇範圍左上角的儲存格，然後再選擇資料的方向。此外，如果請求含有多個期間，您可以選擇期間的方向，然後選擇是否要在各個期間當中略過一定數量的儲存格。
   * **從清單：**&#x200B;可讓您從可新增資料的清單選擇資料。
1. If you enable **[!UICONTROL From List]**, select any available listed items or click **[!UICONTROL Add]**.

   When you click **[!UICONTROL Add]**, the [!UICONTROL Select From List] form displays a list of available dimension values for the current request date range, limited to the first 10,000 items. You can search across these items or click **[!UICONTROL More ...]**, which displays the [!UICONTROL Search Form], so that you can create a more detailed search for dimensions.
1. 在上， [!UICONTROL Select From List]按一下 **[!UICONTROL OK]**。
1. On the [!UICONTROL Choose Page] form, save your Specific filter if you want, then click **[!UICONTROL OK]**.
