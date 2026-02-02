---
title: 在Report Builder中管理資料區塊
description: 瞭解如何在Report Builder中管理資料區塊。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 63e169b3-7e13-405e-83a4-17f2a9917ed2
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 20%

---

# 管理資料區塊

您可以使用[!UICONTROL 資料區塊管理員]，檢視及管理活頁簿中的所有資料區塊。 [!UICONTROL 資料區塊管理員]提供搜尋、篩選和排序功能，讓您找出特定的資料區塊。 在選取一個或多個資料區塊後，您可以編輯、刪除或重新整理所選的資料區塊。

## 檢視資料區塊

若要檢視列出活頁簿中所有資料區塊的表格，請選取![表格管理](/help/assets/icons/TableManage.svg) **[!UICONTROL 管理]**。

![檢視所有資料區塊清單的管理選項。](./assets/image53.png){zoomable="yes"}

**[!UICONTROL 資料區塊管理員]**&#x200B;會顯示一個資料表，其中包含活頁簿中存在的所有資料區塊。

![活頁簿中存在的所有資料區塊清單。](./assets/image52.png){zoomable="yes"}

您可以使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)來選取要顯示的欄。

## 排序資料區塊

您可以依顯示的欄來排序資料區塊表格。 例如，您可以依報表套裝、區段、日期範圍和其他變數排序資料區塊。

若要排序資料區塊表格，請選取欄標題。 選取相同的欄標題來反轉排序順序。


## 搜尋資料區塊

使用![搜尋](/help/assets/icons/Search.svg) **[!UICONTROL _搜尋_]**&#x200B;欄位來尋找資料區塊資料表中的任何專案。 例如，您可以搜尋包含在資料區塊或報表套裝中的量度。 您也可以搜尋出現在日期範圍、修改日期或上次執行日期等欄中的日期。


## 編輯資料區塊

您可以編輯資料區塊的報表套裝和日期範圍。 或套用至資料區塊的區段。

例如，您可以在一或多個資料區塊中以新區段取代現有區段。

1. 選取您想要更新的資料區塊。 您可以選取最上層核取方塊來選取所有資料區塊，也可以選取個別資料區塊。

   ![鉛筆編輯圖示](./assets/image56.png){zoomable="yes"}

1. 選取![編輯](/help/assets/icons/Edit.svg)以顯示&#x200B;**[!UICONTROL 快速編輯]**&#x200B;視窗。

   ![快速編輯視窗](./assets/image58.png){zoomable="yes"}

1. 選取連結以更新報表套裝、日期範圍或區段。 在&#x200B;**[!UICONTROL 快速編輯]** - **[!UICONTROL 區段]**&#x200B;中，您可以新增、移除或更新所選資料區塊的區段。

   ![快速編輯視窗中的新增區段欄位](./assets/image59.png){zoomable="yes"}

## 重新整理資料區塊

選取![重新整理](/help/assets/icons/Refresh.svg)以重新整理資料區塊表格。

若要驗證資料區塊是否已重新整理，請檢視重新整理狀態圖示：

- 成功重新整理的資料區塊顯示![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg)。

- 無法重新整理的資料區塊會顯示![AlertRed](/help/assets/icons/AlertRed.svg)。


## 刪除資料區塊

若要刪除一或多個資料區塊：

1. 選取一或多個資料區塊。
1. 選取「![刪除](/help/assets/icons/Delete.svg)」。
1. 在&#x200B;**[!UICONTROL 刪除資料區塊]**&#x200B;對話方塊中選取&#x200B;**[!UICONTROL 刪除]**，或選取&#x200B;**[!UICONTROL 取消]**&#x200B;以取消刪除。

## 將資料區塊分組

您可以使用&#x200B;**[!UICONTROL 分組方式]**&#x200B;下拉式功能表將資料區塊分組，也可以選取欄標題。

若要依欄排序資料區塊，請選取欄標題。 若要依群組來分組資料區塊，請從&#x200B;**[!UICONTROL 分組方式]**&#x200B;下拉式選單中選取群組名稱。 例如，底下熒幕擷圖顯示依報表套裝分組的資料區塊。

您可以使用分組快速選取要修改其通用元素（如區段）的資料區塊。

![資料區塊管理員顯示[依工作表分組]清單。](./assets/group-data-blocks.png){zoomable="yes"}



<!--

# Manage Data Blocks in Report Builder

You can view and manage all data blocks in a workbook using the Data Block Manager. The Data Block Manager provides search, filter, and sort capabilities that allow you to quickly locate specific data blocks. After selecting one or more data blocks, you can edit, delete, or refresh the selected data blocks.

![The Data block manager screen.](./assets/image52.png)

## View Data Blocks

Click **Manage** to view a list of all data blocks in a workbook.

![The Manage option to view a list of all data blocks.](./assets/image53.png)

The Data Block Manager lists all data blocks present in a workbook. 

## Sort the Data Blocks list

You can sort the data block list by a displayed column. For example, you can sort the data block list by report suites, segments, date range, and other variables.

To sort the data block list, click a column heading.

![Sorting the data blocks.](./assets/image54.png)

## Search the Data Block list

Use the Search field to locate anything in the data block table. For example, you could search for metrics contained in the data blocks or report suite. You can also search for dates appearing in the date range, date modified, or last run date columns.

![Using the Search field to locate anything in the data block table.](./assets/image55.png)

## Edit Data Blocks

You can edit the report suite, date range, or the segments applied to one or more data blocks.

For example, you can replace an existing segment with a new segment in one or more data blocks.

1. Select the data blocks that you want to update. You can select the top-level check box to select all data blocks or you can select individual data blocks.

   ![The pencil edit icon](./assets/image56.png)

1. Click the edit icon to display the Quick edit window.

   ![The Quick edit window](./assets/image58.png)

1. Select a segment link to update report suites, date ranges, or segments.

   ![The Add Segment field in the Quick edit window](./assets/image59.png)

## Refresh Data Blocks

Click the refresh icon to refresh the data blocks in the list.

<img src="./assets/refresh-icon.png" width="15%" alt="Refresh icon"/>

To verify if a data block is refreshed, view the refresh status icon. 

A successfully refreshed data block displays a checkmark in a green circle: <img src="./assets/refresh-success.png" width="5%" alt="Green circle with check mark icon"/>. 

A data block that has failed to refresh displays a warning icon: <img src="./assets/refresh-failure.png" width="5%" alt="Red triangle with exclamation mark icon"/>.This makes it easy to identify if any data blocks have errors.


![Data block manager showing refresh status for each data block listed.](./assets/image512.png)

## Delete a Data Block

1. Select a data block in the Data Block manager. 
1. Click the trash can icon to delete the selected data block.

## Group Data Blocks

You can group data blocks using the **Group by** drop-down menu or you can click a column title. To sort data blocks by column, click the column title. To group data blocks by groups, select a group name from the **Group by** drop-down menu. For example, the screenshot below shows data blocks grouped by Sheet. It shows data blocks grouped by Sheet1 and Sheet2.  This is useful, for example, in the segment-replacing use case. If you have multiple segments applied to each data block, it is helpful to create a group containing all the data blocks that you want to replace. Then you can easily select and edit them all at once.

![Data block manager showing the Group by Sheet list.](./assets/group-data-blocks.png)

## Modify the Data Block Manager view

You can modify which columns are visible in the Data Block Manager window.


Click the column list <img src="./assets/image515.png" width="3%" alt="Column list icon"/> icon to select which columns are listed in the Data Block Manager. Select a column name to display the column. Deselect the column name to remove the column from view.

![Data block manager showing the column list](./assets/image516.png)

-->