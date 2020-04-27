---
description: 說明將篩選條件套用至路徑報表的步驟。
title: 使用請求精靈篩選路徑報表
topic: Report builder
uuid: 9b22d5b5-7ae8-49a2-90ae-0c1075562bbe
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用請求精靈篩選路徑報表

說明將篩選條件套用至路徑報表的步驟。

此範例使用網站區域路徑。

1. In Adobe Report Builder, click **[!UICONTROL Create]** to open the Request Wizard.
1. 選擇正確的報表套裝。
1. 在左側的樹視圖中，選擇 **[!UICONTROL Paths]** > **[!UICONTROL Site Sections]** > **[!UICONTROL Site Section Paths]**。

   ![](assets/site_section_path_1.png)

1. 指定適當的日期。
1. 按一下 **[!UICONTROL Next]**.
1. 在精靈的步驟2中，按一 **[!UICONTROL Row Labels]**&#x200B;下連結 **[!UICONTROL Top 1-10 (pattern applied)]** 。 依預設，在路徑報表中，模式皆已套用。

   ![](assets/site_section_path_2.png)

1. 選取 **[!UICONTROL Filter]** 選項。

   ![](assets/filter_option.png)

1. 在對話 **[!UICONTROL Define 'Site Section Paths' Path Pattern]** 方塊中，您可以指定
   1. 第一份報表的起始排名。
   1. 您希望在此報表中顯示的項目數。
1. Click **[!UICONTROL Edit]** to define a path pattern.
1. If you want a custom pattern, drag and drop any **[!UICONTROL Pattern Objects]** from the list on the left into the **[!UICONTROL Pattern Build Canvas]** on the right.

   ![](assets/custom_pattern.png)

1. You can also select a predefined pattern from the **[!UICONTROL Select a Pattern]** drop-down list and modify it. 可用的模式包括：

   ![](assets/select_a_pattern.png)

   有些模式只適用於 Report Builder：登入路徑的下一個項目模式、退出路徑的前一個項目模式、下一個項目模式。
1. 若要編輯預先定義的模式，
   1. 請選取模式。例如，選擇 **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. 現在，您應該定義使用者在退出前所依循的網站區域路徑。按一下 **[!UICONTROL Specific Item(s): 0 selected]**. 您可以從儲存格範圍 (如果您正在編輯現有的請求) 選取，或是從區段清單選取，以定義此路徑。
   1. To select from a range of cells from a previous request, select **[!UICONTROL From range of cells]** and click the cell selector icon. 接著，從報表中選取儲存格。![](assets/choose_site_section_paths.png)

   1. To select from a list of site sections, select **[!UICONTROL From list]** and click **[!UICONTROL Add]**.
   1. Move elements from the **[!UICONTROL Available Elements]** column to the **[!UICONTROL Selected Elements]** column by selecting them and clicking the orange arrow. 按一下 **[!UICONTROL OK]**。 ![](assets/move_site_section_elements.png)

   1. To save the pattern you just established, click **[!UICONTROL Save]**.
   1. 按三 **[!UICONTROL OK]** 下，然後按一下 **[!UICONTROL Finish]**。 篩選路徑請求便順利產生。
