---
title: Report Builder 中心
description: 瞭解Report Builder中心。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: e18381ea-b7d4-4d7a-9ded-23b2d06fa204
source-git-commit: ff1722416fe5062d16c12185d17271ebc2d6b624
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 22%

---

# Report Builder 中心


Report Builder中心是從Excel功能區列選取![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]**&#x200B;時，Excel活頁簿中顯示的右側窗格。

利用 Report Builder 中心建立、更新、刪除及管理資料區塊。

Report Builder中心包含![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**、![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**&#x200B;和![行事曆](/help/assets/icons/Calendar.svg) **[!UICONTROL 排程]**&#x200B;按鈕、**[!UICONTROL 命令]**&#x200B;面板和&#x200B;**[!UICONTROL 快速編輯]**&#x200B;面板。

![Report Builder中心](assets/hub51.png){zoomable="yes"}


選取

* ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 建立]**&#x200B;以[建立新的資料區塊](create-a-data-block.md)。
* ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL 管理]**&#x200B;以[管理現有的資料區塊](manage-reportbuilder.md)。
* ![行事曆](/help/assets/icons/Calendar.svg) **[!UICONTROL 排程]**&#x200B;至[管理排程，以透過電子郵件傳送您的活頁簿](schedule-reportbuilder.md)。

## 「命令」面板

使用&#x200B;**[!UICONTROL 命令]**&#x200B;面板來存取與選取的儲存格或先前動作相容的命令。

| 命令 | 可提供時間為… | 用途 |
|------|------------------|--------|
| ![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 編輯資料區塊]** | 所選取的儲存格僅為一個資料區塊的一部分。 | 用於編輯資料區塊。 |
| ![重新整理](/help/assets/icons/Refresh.svg) **[!UICONTROL 重新整理資料區塊]** | 選取範圍包含至少一個資料區塊。 指令只會重新整理選取範圍中的資料區塊。 | 用於重新整理一或多個資料區塊。 |
| ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL 重新整理所有資料區塊]** | 該活頁簿包含一或多個資料區塊。 | 用於重新整理活頁簿中的所有資料區塊 |
| ![傳送](/help/assets/icons/Send.svg) **[!UICONTROL 傳送活頁簿]** | 該活頁簿包含一或多個資料區塊。 | 使用以電子郵件[傳送活頁簿為檔案](schedule-reportbuilder.md)。 |
| ![複製](/help/assets/icons/Copy.svg) **[!UICONTROL 複製資料區塊]** | 所選取的儲存格範圍為一或多個資料區塊的一部分。 | 用於複製資料區塊。 |
| ![剪下](/help/assets/icons/Cut.svg) **[!UICONTROL 剪下資料區塊]** | 所選取的儲存格範圍為一或多個資料區塊的一部分。 | 設定以剪下資料區塊。 |
| ![刪除](/help/assets/icons/Delete.svg) **[!UICONTROL 刪除資料區塊]** | 所選取的儲存格僅為一個資料區塊的一部分。 | 用於刪除資料區塊 |

## 快速編輯面板

當您選取試算表中的一個或多個資料區塊時，Report Builder會顯示&#x200B;**[!UICONTROL 快速編輯]**&#x200B;面板。 您可以使用&#x200B;**[!UICONTROL 快速編輯]**&#x200B;面板，同時變更一或多個資料區塊中的引數。

您使用&#x200B;**[!UICONTROL 快速編輯]**&#x200B;區段時所做的變更會套用至所有選取的資料區塊。

### 報告套裝

資料區塊會從選取的報表套裝提取資料。 如果在一個工作表中選取了多個資料區塊，且這些資料區塊不從相同的報表套裝提取資料，則&#x200B;**報表套裝**&#x200B;連結會顯示&#x200B;**[!UICONTROL _多個_]**。

當您變更報表套裝時，選取範圍中的所有資料區塊都會採用新的報表套裝。 資料區塊中的元件會根據ID和新的報表套裝比對。 如果在資料區塊中找不到元件，則會移除該元件，並以&#x200B;**[!UICONTROL 無效值]**&#x200B;取代，或針對特定元件顯示![AlertRed](/help/assets/icons/AlertRed.svg)。

若要變更報表套裝，請從&#x200B;**[!UICONTROL 報表套裝]**&#x200B;下拉式功能表中選取新的報表套裝。


### 日期範圍

**資料範圍**&#x200B;顯示所選取資料區塊的資料範圍。 如果選取具有多個日期範圍的多個資料區塊，**[!UICONTROL 日期範圍]**&#x200B;連結會顯示&#x200B;**[!UICONTROL _多個_]**。

### 區段

**區段**&#x200B;連結會顯示所選資料區塊使用之區段的摘要清單。 如果選取了多個已套用多個區段的資料區塊，**區段**&#x200B;連結會顯示&#x200B;**[!UICONTROL _多個_]**。

>[!MORELIKETHIS]
>
>[選擇報表套裝](select-report-suite.md)
>[選取日期範圍](select-date-range.md)
>[使用篩選器](work-with-segments.md)
>

<!--

Use the Report Builder hub to create, update, delete, and manage data blocks.

The Report Builder hub contains the Create, Manage, and Schedule buttons, the COMMANDS panel, and The QUICK EDIT panel.

<img src="./assets/hub51.png" alt="Report Builder Hub"/>


## Create, Manage, and Schedule buttons

Use the Create, Manage, and Schedule buttons to create new data blocks, manage existing data blocks, or schedule datablocks.

## COMMANDS panel

Use the COMMANDS panel to access commands that are compatible with the selected cells or a previous action.

### Commands

| Commands displayed      | Available when…   | Purpose          |
|------|------------------|--------|
| Edit data block | The selected cell or cells range is part of one data block only. | Used to edit a data block |
| Refresh data block | The selection contains at least one data block. The command refreshes only the data blocks in the selection. | Used to refresh one or more data blocks |
| Refresh all data blocks | The workbook contains one or more data blocks. | Used to refresh ALL data blocks in the workbook |
| Send workbook |   |  Send a workbook on a schedule. |
| Copy data block   | The selected cell or cell range is part of one or more data blocks. | Used to copy a data block   |
| Cut data block |   | Used to cut a data block |
| Delete data block | The selected cell or cells range is part of one data block only. | Used to delete a data block |

## QUICK EDIT panel

When you select one or more data blocks in a spreadsheet, Report Builder displays the QUICK EDIT panel. You can use the QUICK EDIT panel to change parameters in a single data block or to change parameters in multiple data blocks at the same time.

![The Quick Edit panel in Report Builder](./assets/hub2.png)

The changes made using the Quick Edit sections apply to all selected data blocks.

### Report suites

Data blocks pull data from a selected report suite. If multiple data blocks are selected in a worksheet and they don't pull data from the same report suite, the **Report Suites** link displays *Multiple*.

When you change the report suite, all data blocks in the selection adopt the new report suite. Components in the data block are matched to the new report suite based on ID, for example, matching ```evars```). If a component isn't found in a data block, a warning message is displayed and the component is removed from the data block.

To change the report suite, select a new report suite from the drop-down menu.

![The Report Builder Hub showing the report suite drop-down menu.](./assets/image16.png)

### Date range

**[!UICONTROL Date range]** shows the date range for the selected data blocks. If multiple data blocks are selected with multiple date ranges, the **[!UICONTROL Date range]** link displays *Multiple*. [Learn more](/help/analyze/report-builder/select-date-range.md)

### Segments

The **Segments** link displays a summary list of the segments used by the selected data blocks. If multiple data blocks are selected with multiple segments applied, the **Segments** link displays *Multiple*. [Learn more](/help/analyze/report-builder/work-with-segments.md)

-->