---
title: Report Builder中的篩選維度
description: 瞭解如何在Report Builder中篩選維度。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 43f48abf-951d-4fd1-afd4-58304ee5247b
source-git-commit: ba4fe682d717e8a90d87eaa5244a269f49a4a00a
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 33%

---

# 篩選器維度


預設情況下，表格中的每個維度項目會傳回該維度的前 10 個項目。

若要變更每個維度會傳回的維度專案：

1. 在資料區塊中選取儲存格。

1. 在![命令](/help/assets/icons/Edit.svg)面板中選取&#x200B;**[!UICONTROL 編輯]** **[!UICONTROL 編輯資料區塊]**。

1. 選取&#x200B;**[!UICONTROL 下一步]**&#x200B;以顯示&#x200B;**[!UICONTROL 維度]**&#x200B;索引標籤。

1. 選取資料表中元件名稱旁的![MoreSmall](/help/assets/icons/MoreSmall.svg)。

   ![省略符號圖示選項。](./assets/image27.png){zoomable="yes"}

1. 在快顯功能表中選取&#x200B;**[!UICONTROL 篩選維度]**&#x200B;以顯示&#x200B;**[!UICONTROL 篩選維度]**&#x200B;窗格。

1. 選取&#x200B;**最受歡迎**&#x200B;或&#x200B;**特定**&#x200B;作為&#x200B;**[!UICONTROL 型別]**。

   ![在[篩選器]維度窗格中選取的特定選項。](./assets/image28.png){zoomable="yes"}

1. 根據所選的[篩選器型別](#filter-type)選取適當的選項。

1. 選取&#x200B;**[!UICONTROL 套用]**&#x200B;以新增篩選器。

1. Report Builder 會顯示通知，以確認新增的篩選器。

若要顯示已套用的篩選器，可將滑鼠游標停留在維度上。包含已套用篩選器的維度會在維度名稱旁顯示![篩選器](/help/assets/icons/Filter.svg)篩選器圖示。

## 變更篩選器和排序的順序

用來篩選及排序資料區塊的量度旁會出現![向上箭頭](/help/assets/icons/ArrowUp.svg)或![向下箭頭](/help/assets/icons/ArrowDown.svg)。 箭頭的方向會指出量度是以遞增或遞減順序排序。

若要變更排序順序：

- 選取量度旁的![向上鍵](/help/assets/icons/ArrowUp.svg)或![向下鍵](/help/assets/icons/ArrowDown.svg)以切換排序順序。

若要變更用於篩選和排序資料區塊的量度：

1. 將滑鼠游標停留在「表格產生器」中所需的量度元件上，即可顯示更多選項。 

2. 選取![向下箭頭](/help/assets/icons/ArrowDown.svg)作為偏好量度。

   ![資料表產生器和量度。](./assets/image30.png){zoomable="yes"}



## 篩選器類型

有兩種方式篩選維度專案： [最受歡迎](#most-popular)和[特定](#specific-filtering)

### **[!UICONTROL 最熱門]**

**[!UICONTROL 最受歡迎]**&#x200B;選項可讓您根據量度值動態篩選維度專案。 「最受歡迎」會根據量度值傳回排名最高的維度專案。 預設情況下，會出現前 10 個維度項目的清單，從加入資料區塊的第一個量度開始排序。

![最受歡迎的選項。](./assets/image29.png){zoomable="yes"}


#### 「頁面」和「列數」選項

利用&#x200B;**[!UICONTROL 頁面]**&#x200B;和&#x200B;**[!UICONTROL 列數]**&#x200B;欄位，將資料分割成循序群組或頁面。此功能可讓您將排名的列值而不是最高的值提取到您的報表中。 在提取超過50,000列上限的資料時，此外掛程式特別實用。

頁面的預設值為`1`，而列的預設值為`10`。 這些預設值表示每個頁面有10列資料。 頁面 1 會傳回前 10 個項目，而頁面 2 則傳回接下來的 10 個項目，以此類推。

以下表格列出了頁面和列數值以及結果輸出的範例。

| 頁面 | 列 | 輸出 |
|------|--------|----------------------|
| 1 | 10 | 前 10 個項目 |
| 2 | 10 | 項目 11 至 20 |
| 1 | 100 | 前 100 個項目 |
| 2 | 100 | 項目 101 至 200 |
| 2 | 50,000 | 項目 50,001 至 100,000 |

下表列出頁面和列的最小值和最大值。

|       | 最小值 | 最大值 |
|-------|---------------:|---------------:|
| 起始頁面 | 1 | 5千萬 |
| 列數 | 1 | 50,000 |


#### 包括「無值」

在Customer Journey Analytics中，某些維度會收集&#x200B;*沒有值*&#x200B;專案。 **[!UICONTROL 包含「沒有值」]**&#x200B;設定可讓您從報表中排除這些值。 例如，您可以根據產品 SKU 金鑰建立「產品名稱」之類的分類。如果特定產品SKU尚未以其特定「產品名稱」分類設定，其「產品名稱」值會設為&#x200B;*無值*。

預設會選取&#x200B;**[!UICONTROL 包含[沒有值]]**。 取消選取此選項，即可排除包含無值的輸入項。

#### 依「準則」篩選

您可根據是否符合所有準則或任何準則來篩選維度項目。

若要設定篩選條件，請執行下列動作：

1. 從運運算元下拉式選單中選取運運算元。 依預設，已選取&#x200B;**[!UICONTROL 包含片語]**

   ![運運算元清單。](./assets/image31.png){zoomable="yes"}

1. 輸入搜尋字詞。

1. 選取![新增](/help/assets/icons/Add.svg) **[!UICONTROL 新增列]**&#x200B;以確認選取範圍並新增另一個條件專案。

1. 選取![CrossSize75](/help/assets/icons/CrossSize75.svg)以移除條件專案。

您可包括最多 10 個準則項目。

### **[!UICONTROL 特定]**

**[!UICONTROL 特定]**&#x200B;選項可讓您為每個維度建立固定的維度專案清單。 使用&#x200B;**[!UICONTROL 特定]**&#x200B;篩選類型，即可指定包含您的篩選條件的精確維度項目。您可從清單或是儲存格範圍選取項目。

![特定選項和選取的專案。](./assets/image32.png){zoomable="yes"}

#### 從清單

1. 選取&#x200B;**[!UICONTROL 從清單]**&#x200B;選項，即可搜尋和選取維度項目。

   當您選取&#x200B;**從清單**&#x200B;選項時，**[!UICONTROL Dimension專案]**&#x200B;清單會填入維度專案，並依事件數量排序。

   ![從清單選項和可用專案。](./assets/image33.png){zoomable="yes"}

1. 在![搜尋](/help/assets/icons/Search.svg) **[!UICONTROL _新增專案_]**&#x200B;中輸入搜尋字詞，以搜尋清單。

1. 若要搜尋未包含在過去90天資料中的專案，請選取&#x200B;**[!UICONTROL 顯示過去6個月的專案]**&#x200B;以擴大搜尋。 在過去6個月的資料載入後，Report Builder會將連結更新為&#x200B;**[!UICONTROL 顯示過去18個月的專案]**。

1. 若要從&#x200B;**[!UICONTROL 選取的專案]**&#x200B;清單中刪除專案，請選取![CrossSize75](/help/assets/icons/CrossSize75.svg)。

1. 若要移動&#x200B;**[!UICONTROL 選取的專案]**&#x200B;清單中的專案，請拖放該專案或選取![MoreSmall](/help/assets/icons/MoreSmall.svg)以顯示內容功能表，並從移動選項中選取。

1. 選取&#x200B;**[!UICONTROL 「套用」]**。

Report Builder 會更新清單，以顯示您套用的特定篩選條件。

#### 從儲存格範圍

選取&#x200B;**從儲存格範圍**&#x200B;選項，以選擇包含要比對的維度專案清單的儲存格範圍。

![從儲存格範圍選項和欄位選取一個儲存格範圍。](./assets/image37.png){zoomable="yes"}

當您選取儲存格範圍時，請考量以下限制：

- 範圍必須至少包括一個儲存格。
- 範圍不能超過 50,000 個以上的儲存格。
- 範圍必須為單一連續的列或欄。

您的選取範圍可包含空白儲存格或是裡面的值和特定維度項目不相符的儲存格。


### 快速篩選維度

若要篩選目前未套用篩選器的維度：

1. 選取維度的![V形右側](/help/assets/icons/ChevronRight.svg)。 例如，**[!UICONTROL 互動管道]**。

1. 連按兩下要新增至篩選器的維度專案。 或者，選取一或多個維度專案，並將選取專案拖放至![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]**&#x200B;區段。

   ![維度索引標籤和維度清單。](./assets/quickly-filter.png){zoomable="yes"}


<!--

By default, each dimension item in the table returns the top 10 items for that dimension.

To change the dimension items returned for each dimension

1. Click **[!UICONTROL Manage]** and select a data block from the list.

   ![Manage > Edit data block](./assets/manage-edit.png)

1. Click **[!UICONTROL Edit data block]** in the COMMANDS panel.

1. Click **[!UICONTROL Next]** to display the Dimensions tab.

1. Click the **...** icon next to a component name in the table.

    ![The ellipsis icon options.](./assets/image27.png)

1. Select **[!UICONTROL Filter dimension]** in the pop-up menu to display the **[!UICONTROL Filter dimension]** pane.

1. Select **[!UICONTROL Most popular]** or **[!UICONTROL Specific]**.

    ![The specific option selected in the Filter dimension pane.](./assets/image28.png)

1. Select appropriate options based on the filter type chosen.

1. Click **[!UICONTROL Apply]** to add the filter.

    Report Builder displays a notification to confirm the added filter.

To display applied filters, hover over a dimension. Dimensions with applied filters display a filter icon to the right of the Dimension name.

## Filter Type

There are two ways to filter dimension items: Most popular and Specific.

## Most popular

The [!UICONTROL Most popular] option allows you to dynamically filter dimension items based on metric values. [!UICONTROL Most popular] filtering returns the highest ranked dimension items based on metric values. By default, the first 10 dimensions items are listed, sorted by the first metric added to the data block.

 ![The Most popular option.](./assets/image29.png)


### Page and Rows options

Use the **Page** and **Rows** fields to divide data into sequential groups or pages. This allows you to pull ranked row values other than the top-most values into your report. This feature is especially useful for pulling data beyond the 50,000 row limit.

#### Page and Rows defaults

- Page = 1
- Rows = 10

The Page and Rows default settings identify that each page has 10 rows of data. Page 1 returns the top 10 items, page 2 returns the next 10 items, and so on.

The table below lists examples of page and row values and the resulting output.

| Page | Row    | Output               |
|------|--------|----------------------|
| 1    | 10     | Top 10 items         |
| 2    | 10     | Items 11-20          |
| 1    | 100    | Top 100 items        |
| 2    | 100    | Items 101-200        |
| 2    | 50,000 | Items 50,001-100,000 |

#### Minimum and maximum values

- Starting page: Min = 1, Max: 50 million
- Number of rows: Min = 1, Max: 50,000

### Include "No value"

In Adobe Analytics, some dimensions collect a "no value" entry. This filter allows you to exclude these values from reports. For example, you can create a classification such as the Product Name classification based on the Product SKU key. If a specific product SKU has not been set up with its specific Product Name classification, its Product Name value is set to "no value".

Include "**No value**" is selected by default. Deselect this option to exclude entries with no value.

### Filter by Criteria

You can filter dimension items based on whether all criteria are met or if any criteria are met.

To set filtering criteria

1. Select an operator from the drop-down list.

    ![The operator list.](./assets/image31.png)

1. Enter a value into the search field.

1. Click **[!UICONTROL Add row]** to confirm the selection and add another criteria item.

1. Click the delete icon to remove a criteria item.

    You can include up to 10 criteria items.

### Change the filter and sort order

An arrow appears next to the metric used to filter and sort the data block. The direction of the arrow indicates whether the metric is sorted greatest to least or least to greatest.

To change the sort direction, click the arrow next to the metric.

To change the metric used to filter and sort the data block,

1. Hover over the desired metric component in the Table builder to display additional options.

2. Click the arrow on the preferred metric.

   ![The Table builder and metrics.](./assets/image30.png)


## Specific filtering

The Specific option allows you to create a fixed list of dimension items for each dimension. Use the **[!UICONTROL Specific]** filtering type to specify the exact dimension items to include in your filter. You can select items from a list or from a range of cells.

![The Specific options and selected items.](./assets/image32.png)

### From list

1. Select the **[!UICONTROL From list]** option to search for and select dimension items.

    When you select the **[!UICONTROL From list]** option, the list is populated with dimension items with the most events first.

    ![The From list option and available items.](./assets/image33.png)

    The **[!UICONTROL Available items]** list is ordered from dimension items with the most events to those with the least.

1. Enter a search term in the **[!UICONTROL Add item]** field to search the list.

1. To search for an item not included in the last 90 days of data, click **[!UICONTROL Show items for the last 6 months]** to extend the search.

    ![The Show items from the last 6 months list.](./assets/image34.png)

    After data from the past 6 months loads, Report Builder updates the link to **[!UICONTROL Show items for last 18 months]**.

1. Select a dimension item.

    Selected dimension items are automatically added to the **[!UICONTROL Selected items]** list.

    ![](./assets/image35.png)

    To delete an item from the list, click the delete icon to remove the item from the list.

    To move an item in the list, drag and drop the item or click ... to display the move menu.

    ![The dimension items list.](./assets/image36.png)

1. Click **[!UICONTROL Apply]**

    Report Builder updates the list to show the specific filtering you applied.

### From range of cells

Select the **[!UICONTROL From range of cells]** option to choose a range of cell that contain the list of dimensions items to match.

 ![The From range of cells option and field to select one range of cells.](./assets/image37.png)

When you select a range of cells, consider the following restrictions:

- The range must have at least one cell.
- The range can't have more than 50,000 cells.
- The range must be in a single uninterrupted row, or column.

Your selection can contain empty cells or cells with values that don't match with a specific dimension item.

### From the Dimensions tab in the Table builder

From the **[!UICONTROL Dimensions]** tab, click the chevron icon next to a dimension name to view the list of dimension items.

 ![The Dimensions tab and the list of dimensions.](./assets/dimensions_chevron.png)

You can drag and drop items onto the **[!UICONTROL Table]** or double-click an item name to add it to the **[!UICONTROL Table]** builder.

-->