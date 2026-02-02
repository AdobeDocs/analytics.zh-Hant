---
title: 在Report Builder中建立資料區塊
description: 瞭解如何建立資料區塊。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: fd3ff12a-14de-46f6-ab89-a0152fb11b0d
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 20%

---

# 建立資料區塊

*資料區塊*&#x200B;是由單一資料請求所建立的資料表。Report Builder 活頁簿可包含多個資料區塊。當您建立資料區塊時，請先設定資料區塊，然後再建置資料區塊。

## 設定資料區塊

為資料區塊位置、報表套裝和日期範圍設定初始資料區塊引數。

1. 選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 建立]**。

   ![顯示[建立資料區塊]選項的熒幕擷圖](./assets/create-data-block.png){zoomable="yes"}


1. 設定&#x200B;**[!UICONTROL 資料區塊地點]**。

   資料區塊位置選項會定義Report Builder將資料新增至工作表的工作表位置。

   若要指定資料區塊位置，請在工作表中選取單一儲存格或輸入儲存格位址，例如`a3`、`\\\$a3`、`a\\\$3`或`sheet1!a2`。 擷取資料時，指定的儲存格會變成資料區塊的左上角。

   使用![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)從工作表中目前選取的儲存格中挑選資料區塊位置。

1. 選擇&#x200B;**[!UICONTROL 報表套裝]**。

   「報表套裝」選項可讓您從下拉式功能表選擇報表套裝，或從儲存格位置參考報表套裝。

   選取![DataViewSelector](/help/assets/icons/DataViewSelector.svg)以從儲存格建立報表套裝。

1. 設定&#x200B;**[!UICONTROL 日期範圍]**。

   **[!UICONTROL 日期範圍]**&#x200B;選項可讓您選擇日期範圍。 日期範圍可以是固定或滾動式。

   選取「**[!UICONTROL 行事曆]**」以使用「![行事曆](/help/assets/icons/Calendar.svg)」挑選資料範圍，或手動輸入日期範圍。 您可以選擇從&#x200B;**[!UICONTROL _搜尋預設集_]**&#x200B;下拉式功能表中選取預設集。

   選取&#x200B;**[!UICONTROL 從儲存格]**&#x200B;以根據目前工作表中的儲存格定義開始和結束資料。

   如需日期範圍選項的詳細資訊，請參閱[選取日期範圍](select-date-range.md)。

1. 選取&#x200B;**[!UICONTROL 「下一步」]**。

   ![顯示日期範圍選項和作用中[下一步]按鈕的熒幕擷圖。](./assets/choose_date_data_view3.png)

   設定資料區塊後，您可以選取維度、量度和區段來建置資料區塊。 **[!UICONTROL 維度]**、**[!UICONTROL 量度]**&#x200B;和&#x200B;**[!UICONTROL 區段]**&#x200B;索引標籤會顯示在&#x200B;**[!UICONTROL 表格]**&#x200B;窗格上方。

## 建置資料區塊

若要建置資料區塊，請選取報表元件，然後自訂版面配置。

1. 新增&#x200B;**[!UICONTROL 維度]**、**[!UICONTROL 量度]**&#x200B;和&#x200B;**[!UICONTROL 區段]**&#x200B;元件。

   捲動元件清單或使用![搜尋](/help/assets/icons/Search.svg) **[!UICONTROL _搜尋元件_]**&#x200B;欄位來尋找元件。 將元件拖放至[!UICONTROL 表格]窗格，或在清單中重複選取元件名稱，以將元件新增至[!UICONTROL 表格]窗格。

   連按兩下元件，將該元件新增至表格的預設區段。

   - Dimension元件已新增至![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]**&#x200B;區段，或新增至![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**&#x200B;區段（如果您在欄中已經有維度）。
   - 日期元件已新增至![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**&#x200B;區段。
   - 區段元件已新增至![區段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 區段]**&#x200B;區段。
   - 已將量度元件新增至![事件](/help/assets/icons/Event.svg) **[!UICONTROL 值]**&#x200B;區段。

1. 安排「表格」窗格中的項目，以自訂資料區塊的版面配置。

   拖放表格窗格中每個清單內的元件，以重新排序元件，或選取![MoreSmall](/help/assets/icons/MoreSmall.svg)，然後選取![向上箭頭](/help/assets/icons/ArrowUp.svg)、向上箭頭![、向下箭頭](/help/assets/icons/ArrowDown.svg)、以及更多以移動清單內的元件。

   當您將元件加入表格時，工作表中的「資料區塊」位置會顯示資料區塊的預覽。資料區塊預覽的版面配置會隨著您新增、移動或移除表格中的項目而自動更新。

   ![熒幕擷圖顯示新增的元件和更新的工作表。](./assets/image10.png)


1. 選擇性地將&#x200B;**[!UICONTROL 開始日期]**&#x200B;設定為維度，以識別資料區塊的開始日期。 如果您有週期性排程報表，且報表具有滾動式日期範圍，則新增開始資料為維度會很有幫助。 或者，如果您有非常規的日期範圍，並且您需要明確說明開始日期。

   ![熒幕擷圖顯示維度清單中的開始日期。](./assets/start-date-dimension.png)

1. 選擇性地顯示或隱藏列與欄標題。 若要這麼做：

   1. 選取&#x200B;**[!UICONTROL 表格]** ![設定](/help/assets/icons/Setting.svg)設定圖示。

      ![顯示[資料表設定]選項的熒幕擷圖。](./assets/table-settings.png)

   1. 核取或取消核取&#x200B;**[!UICONTROL 顯示列與欄標題]**&#x200B;的選項。 預設會顯示標題。

1. 或者，您也可以隱藏或顯示維度標籤和量度標題。 若要這麼做：

   1. 在維度標籤或欄標題上選取![MoreSmall](/help/assets/icons/MoreSmall.svg)以顯示內容功能表。

      ![列區段中的省略符號圖示。](./assets/row-heading.png)

   1. 選取![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]**&#x200B;或![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]**&#x200B;以切換維度標籤或欄標題。 預設會顯示所有標籤。

1. 選取&#x200B;**[!UICONTROL 完成]**&#x200B;以完成資料區塊的設定。

1. 擷取分析資料時，會顯示處理訊息&#x200B;**[!UICONTROL #BUSY]**。

   ![處理訊息。](./assets/image11.png)

1. Report Builder 會擷取資料，並在工作表中顯示已完成的資料區塊。

   ![完成的資料區塊。](./assets/image12.png)


>[!MORELIKETHIS]
>
>[選擇報表套裝](select-report-suite.md)
>[選取日期範圍](select-date-range.md)
>[篩選維度](filter-dimensions.md)
>[使用區段](work-with-segments.md)
>


<!--

A *data block* is the table of data created by a single data request. A Report Builder workbook can contain multiple data blocks. When you create a data block, first configure the data block and then build the data block.

## Configure the data block

Configure the initial data block parameters for the data block location, report suite, and a date range.

1. Click **[!UICONTROL Create]**.

    ![Screenshot showing the Create data block option.](./assets/create_db.png)

1. Set the **[!UICONTROL Data block location]**.

    The data block location option defines the worksheet location where report builder adds the data to your worksheet.

    To specify the data block location, select a single cell in the worksheet and click the icon next to **[!UICONTROL Data block location]**: 
    
    You can also enter a cell address such as a3, \\\$a3, a\\\$3 or sheet1!a2. The cell specified marks the upper-left corner of the data block when the data is retrieved.

1. Choose a **Report Suite**.

    The report suites option allows you to choose a report suite from a drop-down menu or to reference a report suite from a cell location.

1. Set the **[!UICONTROL Date range]**.

    The Date range option allows you to choose a date range. Date ranges may be fixed or rolling. For information about data range options, see [Select a Date Range](select-date-range.md).

1. Click **[!UICONTROL Next]**.

    ![Screenshot showing the date range option and the active Next button.](./assets/choose_date_report_suite.png)

    After you configure the data block, you can select dimensions, metrics, and segments to build your data block. The Dimensions, Metrics, and Filters tabs are displayed above the Table builder pane.

## Build the data block

To build the data block, select report components, and then customize the layout.

1. Add Dimensions, Metrics, and Segments.

    Scroll the component lists or use the **[!UICONTROL Search]** field to locate components. Drag and drop components to the Table pane or double-click a component name in the list to automatically add the component to the Table pane.

    Double-click a component to add it to a default section of the table.

    - Dimension components are added to the Row section or to the Column section if you have a dimension already in the columns.
    - Date components are added to the Column section.
    - Segment components are added to the Segments section.

    **Start date as a Dimension**

    Set the **[!UICONTROL Start date]** as a dimension to clearly identify the start date of your data block. This is helpful if you have a regularly scheduled report that has a rolling date range or if you have an unconventional date range and you need to be clear on the start date.

    ![Screenshot showing the Start date in the list of dimensions.](./assets/start-date-dimension.png){width="30%"}

1. Arrange the items in the Table pane to customize the layout of your data block.

    Drag and drop components in the Table pane to reorder components or right-click a component name and select from the options menu.

    When you add components to the table, a preview of the data block is displayed at the Data block location in the worksheet. The layout of the data block preview automatically updates as you add, move, or remove items in the table.

    ![Screenshot showing the added components and updated worksheet.](./assets/image10.png)

    **Display or hide row and column headers**

1. Click the **[!UICONTROL Table settings]** icon.

    ![Screenshot showing the Table settings option.](./assets/table-settings.png){width="35%"}

1. Check or uncheck the option to Display row and column headers. The headers are displayed by default.

    **Hide or show dimension labels and metric headers**

1. Click the ellipsis icon on either the dimensions or the column headers to display the settings.

    ![The ellipsis icon in the Row section.](./assets/row-heading.png){width="35%"}

1. Click Hide or Show to toggle the dimension labels or column headers. All labels are displayed by default.

1. Click **[!UICONTROL Finish]**.

    A processing message is displayed while the analytics data is retrieved.

    Report Builder retrieves the data and displays the completed data block in the worksheet.

    ![The completed data block.](./assets/image12.png)

-->