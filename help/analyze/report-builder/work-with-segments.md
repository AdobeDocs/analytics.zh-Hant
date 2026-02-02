---
title: 在Report Builder中使用區段
description: 瞭解如何在Report Builder中使用區段。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 2691fde0-59c6-45a7-80a5-8e5e221adce2
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 6%

---

# 使用區段

當您建立新的資料區塊或從&#x200B;**[!UICONTROL 命令]**&#x200B;面板選取&#x200B;**[!UICONTROL 編輯資料區塊]**&#x200B;時，可以套用區段。

## 將區段套用至資料區塊

若要將區段套用至整個資料區塊，請連按兩下區段，或從元件清單中將區段拖放至「表格」的區段區段中。

## 將篩選器套用至個別量度

若要使用區段將篩選器套用至個別量度：

* 從&#x200B;**[!UICONTROL 區段]**&#x200B;將一或多個區段拖放至表格中的量度上。

* 或者：

   1. 選取![表格](/help/assets/icons/MoreSmall.svg)窗格中特定量度的&#x200B;**[!UICONTROL MoreSmall]**，然後選取&#x200B;**[!UICONTROL 篩選量度]**。

      ![區段索引標籤顯示量度。](./assets/filter-metric.png){zoomable="yes"}

   1. 從&#x200B;**[!UICONTROL 區段]**&#x200B;下拉式功能表中選取一或多個區段。 區段已新增至&#x200B;**[!UICONTROL 套用的區段]**&#x200B;清單。

      ![已套用區段](assets/segments-applied.png)
   1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從&#x200B;**[!UICONTROL 套用的區段]**&#x200B;清單中移除區段。 或選取&#x200B;**[!UICONTROL 全部清除]**&#x200B;以從&#x200B;**[!UICONTROL 套用的區段]**&#x200B;清單中移除所有區段。
   1. 選取&#x200B;**[!UICONTROL 「套用」]**。

若要檢視已套用的篩選器，可將滑鼠游標停留在「表格」窗格中的量度上或選取量度。含有已套用區段的量度會顯示區段圖示。


## 快速編輯區段

您可以使用&#x200B;**[!UICONTROL 快速編輯]**&#x200B;面板來新增、移除或取代現有資料區塊的區段。

當您選取試算表中的儲存格範圍時，**[!UICONTROL 快速編輯]**&#x200B;面板中的&#x200B;**[!UICONTROL 區段]**&#x200B;連結會顯示該選取範圍中的資料區塊所使用區段的摘要清單。

若要使用&#x200B;**[!UICONTROL 快速編輯]**&#x200B;面板編輯區段：

1. 請從一或多個資料區塊選取儲存格範圍。

1. 選取&#x200B;**[!UICONTROL 區段]**&#x200B;連結以啟動&#x200B;**[!UICONTROL 快速編輯]** **[!UICONTROL 區段]**&#x200B;面板。


### 新增或移除區段

您可以使用「新增/移除」選項來新增或移除區段。

1. 選取&#x200B;**[!UICONTROL 快速編輯]** **[!UICONTROL 區段]**&#x200B;面板中的&#x200B;**[!UICONTROL 新增/移除]**&#x200B;索引標籤。


   1. 從&#x200B;**[!UICONTROL 區段]**&#x200B;下拉式功能表中選取一或多個區段。 區段已新增至&#x200B;**[!UICONTROL 套用的區段]**&#x200B;清單。
   1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以從&#x200B;**[!UICONTROL 套用的區段]**&#x200B;清單中移除區段。
   1. 選取&#x200B;**[!UICONTROL 「套用」]**。

Report Builder會顯示訊息，以確認套用的區段變更。

### 取代區段

您可以使用其他區段取代現有區段，以變更資料的分段方式。

1. 在&#x200B;**[!UICONTROL 快速編輯]** **[!UICONTROL 區段]**&#x200B;面板中選取&#x200B;**[!UICONTROL 取代]**&#x200B;索引標籤。

1. 使用&#x200B;**搜尋清單**&#x200B;搜尋欄位來尋找特定區段。

1. 選取一或多個要取代的區段。

1. 從「取代為」下拉式選單搜尋一或多個區段，以將區段新增至「**[!UICONTROL 取代為]**」清單。

1. 選取&#x200B;**[!UICONTROL 「套用」]**。

Report Builder會更新區段清單以反映取代結果。

## 從儲存格定義資料區塊區段

資料區塊可參考儲存格中的區段。 多個資料區塊可參考區段的相同儲存格，讓您一次輕鬆切換多個資料區塊的區段。

若要從儲存格套用區段：

1. [建立新的資料區塊](create-a-data-block.md#create-a-data-block)或編輯現有的資料區塊。
1. 選取&#x200B;**[!UICONTROL 區段]**&#x200B;索引標籤以定義區段。
1. 選取![DataViewSelector](/help/assets/icons/DataViewSelector.svg)。

   ![從儲存格選取區段](assets/select-segment-from-cell.png){zoomable="yes"}

1. 選取您要資料區塊參照區段的儲存格。

1. 連按兩下以新增區段至儲存格。 或者，將一或多個區段拖放至&#x200B;**[!UICONTROL 包含區段]**&#x200B;區段。

1. 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以建立參考儲存格。

1. 從&#x200B;**區段**&#x200B;索引標籤，將新建立的參考儲存格區段新增至您的資料區塊。

   ![區段索引標籤顯示Sheet1！J1（所有資料）區段已新增至資料表。](assets/segment-from-cell-applied.png){zoomable="yes"}

1. 選取&#x200B;**[!UICONTROL 「完成」]**。

若要將參照儲存格當做區段套用至其他資料區塊，請在&#x200B;**[!UICONTROL 表格]**&#x200B;索引標籤的&#x200B;**[!UICONTROL 區段]**&#x200B;清單中，將儲存格參照當做區段之一。

### 使用參考儲存格來變更資料區塊區段

1. 選取試算表中的參考儲存格。

1. 在&#x200B;**[!UICONTROL 快速編輯]**&#x200B;功能表的&#x200B;**[!UICONTROL 儲存格]**&#x200B;區段底下選取連結。

   顯示Sheet1！J1 （所有資料）的儲存格連結中的![區段](assets/select-segment-from-cell-in-sheet.png){zoomable="yes"}

1. 從下拉式選單中選取您的區段。

1. 選取&#x200B;**[!UICONTROL 「套用」]**。

<!--
You can apply segments when you create a new data block or when you select the **Edit data block** option from the COMMANDS panel.

## Apply segments to a data block

To apply a segment to the entire data block, double-click a segment or drag and drop filters from the components list into the Segments section of the Table.

## Apply segments to individual metrics

To apply segments to individual metrics, drag and drop a segment onto a metric in the table. You can also click the **...** icon to the right of a metric in the Table pane and then select **[!UICONTROL Segment metric]**. To view applied segments, hover over or select a metric in the Table pane. Metrics with applied segments display a filter icon.

![Segments tab displaying metrics.](./assets/filter_by.png)

## Quick edit segments

You can use the Quick edit panel to add, remove, or replace segments for existing data blocks.

When you select a range of cells in the spreadsheet, the **[!UICONTROL Segments]** link in the Quick edit panel displays a summary list of the segments used by the data blocks in that selection.

To edit segments using the Quick edit panel

1. Select a range of cells from one or multiple data blocks.

    ![Quick Edit segment panel showing segment options for report suites, date range, and segments.](./assets/select_multiple_dbs.png)

1. Click the link underneath **[!UICONTROL Segments]** to launch the Quick edit - Filters panel.

    ![the Segments panel showing the Add Segments field and Segments Applied lists.](./assets/quick_edit_filters.png)

### Add or remove a segment

You can add or remove segments using the Add/Remove options.

1. Select the **[!UICONTROL Add/Remove]** tab in the Quick edit-segments panel.

    All segments applied to the selected data blocks are listed in the Quick Edit-segments panel. Segments applied to all data blocks in the selection are listed under the **[!UICONTROL Applied to all selected data blocks]** heading. Segments applied to some but not all data blocks are listed under the **[!UICONTROL Applied to 1 or more selected data blocks]** heading.

    When multiple segments are present in the selected data blocks, you can search for specific segments using the **[!UICONTROL Add Filter]** search field.

    ![The Add Segments field.](./assets/add_filter.png)

1. Add segments by selecting segments from the **[!UICONTROL Add segment]** drop down menu.

    The list of searchable segments includes all segments accessible to the report suites that are present in one or more of the selected data blocks as well as all the segments that are available globally in the organization.

    Adding a segment applies the segment to all data blocks in the selection.

1. To remove segments, click the delete icon **x** to the right of segments in the **[!UICONTROL Segments applied]** list.

1. Click **[!UICONTROL Apply]** to save changes and return to the hub panel.

    Report Builder displays a message to confirm the applied segment changes.

### Replace a segment

You can replace an existing segment with another segment to change how the data is segmented.

1. Select the **[!UICONTROL Replace]** tab in the Quick edit-segment panel.

    ![Select the Replace tab.](./assets/replace_filter.png)

1. Use the **[!UICONTROL Search list]** search field to locate specific segments.

1. Choose one or more segments that you want to replace.

1. Search for one or more segments in the Replace with field.

    Selecting a filter adds it to the **[!UICONTROL Replace with]**... list.

1. Click **[!UICONTROL Apply]**.

    Report Builder updates the list of segments to reflect the replacement.

### Define data block segments from cell

Data blocks can reference segments from a cell. Multiple data blocks can reference the same cell for segments, allowing you to easily switch segments for multiple data blocks at a time.

To apply segments from a cell

1. Navigate to Step 2 in either the data block creation or editing process. See [Create a Data Block](./create-a-data-block.md).
1. Click the **[!UICONTROL Segments]** tab to define filters.
1. Click **[!UICONTROL Create segment from cell]**.

    ![Create segment from cell icon.](./assets/create-filter-from-cell.png)

1. Select the cell from which you want the data blocks to reference a segment.
   
1. Add the segment choice you wish to add to the cell by either double clicking the segment, or by dragging and dropping it into the **[!UICONTROL Segments Included]** section. 
   
   Note: Only one choice may be selected for the given cell at one time.

    ![The Add segment from cell window showing the Filters included.](./assets/select-filters.png)

1. Click **[!UICONTROL Apply]** to create the reference cell.

1. From the **[!UICONTROL Segments]** tab, add the newly created reference cell segments to your data block.

    ![Segments tab showing Sheet1!J1(All Data) segment added to the table.](./assets/reference-cell-filter.png)

1. Click **[!UICONTROL Finish]**.

    Now this cell can be referenced by other data blocks in their segments. To apply the reference cell as a segment to other data blocks, simply add the cell reference to their segments from the Segments tab. 

#### Use the reference cell to change data block segments

1. Select the reference cell in your spreadsheet.

1. Click the link under **[!UICONTROL Segments from Cell]** in the Quick Edit menu.

    ![Segments from cell link showing Sheet1!J1 (All Data)](./assets/filters-from-cell-link.png)

1. Select your segment from the drop-down menu.

    ![Segments drop down menu](./assets/filter-drop-down.png)

1. Click **[!UICONTROL Apply]**.
-->