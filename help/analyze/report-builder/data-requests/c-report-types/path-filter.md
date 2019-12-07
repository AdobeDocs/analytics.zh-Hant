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
1. In the tree view on the left, select **[!UICONTROL Paths]** &gt; **[!UICONTROL Site Sections]** &gt; **[!UICONTROL Site Section Paths]**.

   ![](assets/site_section_path_1.png)

1. 指定適當的日期。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. In Step 2 of the Wizard, under **[!UICONTROL Row Labels]**, click the **[!UICONTROL Top 1-10 (pattern applied)]** link. 依預設，在路徑報表中，模式皆已套用。

   ![](assets/site_section_path_2.png)

1. Select the **[!UICONTROL Filter]** option.

   ![](assets/filter_option.png)

1. In the **[!UICONTROL Define 'Site Section Paths' Path Pattern]** dialog, you can specify
   1. 第一份報表的起始排名。
   1. 您希望在此報表中顯示的項目數。
1. Click **[!UICONTROL Edit]** to define a path pattern.
1. If you want a custom pattern, drag and drop any **[!UICONTROL Pattern Objects]** from the list on the left into the **[!UICONTROL Pattern Build Canvas]** on the right.

   ![](assets/custom_pattern.png)

1. You can also select a predefined pattern from the **[!UICONTROL Select a Pattern]** drop-down list and modify it. 可用的模式包括:

   ![](assets/select_a_pattern.png)

   有些模式只適用於 Report Builder : 登入路徑的下一個項目模式、退出路徑的前一個項目模式、下一個項目模式。
1. 若要編輯預先定義的模式，
   1. 請選取模式。For example, select the **[!UICONTROL Exited Site Pattern]**: ![](assets/exited_site_pattern.png)

   1. 現在，您應該定義使用者在退出前所依循的網站區域路徑。Click **[!UICONTROL Specific Item(s): 0 selected]**. 您可以從儲存格範圍 (如果您正在編輯現有的請求) 選取，或是從區段清單選取，以定義此路徑。
   1. To select from a range of cells from a previous request, select **[!UICONTROL From range of cells]** and click the cell selector icon. Then pick the cells from the report. ![](assets/choose_site_section_paths.png)

   1. To select from a list of site sections, select **[!UICONTROL From list]** and click **[!UICONTROL Add]**.
   1. Move elements from the **[!UICONTROL Available Elements]** column to the **[!UICONTROL Selected Elements]** column by selecting them and clicking the orange arrow. The click **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. To save the pattern you just established, click **[!UICONTROL Save]**.
   1. Click **[!UICONTROL OK]** three times and then click **[!UICONTROL Finish]**. 篩選路徑請求便順利產生。
