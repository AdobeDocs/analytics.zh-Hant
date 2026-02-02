---
title: 在Report Builder中選取資料範圍
description: 瞭解如何在Report Builder中選取日期範圍。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 610ce2c8-8ff6-4434-912f-3015cc56a51e
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 46%

---

# 選取日期範圍

若要變更現有資料區塊的日期範圍：

- 選取&#x200B;**[!UICONTROL 編輯資料區塊]**，或
- 在&#x200B;**[!UICONTROL 快速編輯]**&#x200B;中選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;連結。

使用下列選項變更資料區塊的日期範圍。

## 行事曆

**[!UICONTROL 行事曆]**&#x200B;選項可讓您使用下列選項建立靜態或滾動日期：

### 日期範圍

日期範圍欄位會顯示資料區塊請求的目前日期範圍。 您可以直接輸入日期，或使用![行事曆](/help/assets/icons/Calendar.svg)指定日期範圍。

![日期範圍行事曆](assets/date-range-calendar.png){zoomable="yes"}

### 預設集

使用預設集下拉式選單來選取預設集。 您也可以輸入文字來搜尋預設集。

![日期範圍預設集](assets/date-range-presets.png){zoomable="yes"}

此預設下拉式選單包括一組標準預設日期範圍和您儲存或與您共用的報表套裝的日期範圍元件。

### 遞延日期

若要定義遞延日期，請執行下列步驟：

![USe遞延日期](assets/date-range-rolling-date.png){zoomable="yes"}

1. 選取&#x200B;**[!UICONTROL 使用遞延日期]**&#x200B;來定義遞延日期定義的邏輯。 您可以選取方括弧中的文字（例如&#x200B;**[!UICONTROL 固定開始 — 每日滾動]**）來延伸面板，並指定&#x200B;**[!UICONTROL 開始]**&#x200B;和&#x200B;**[!UICONTROL 結束]**&#x200B;的詳細資料。

1. 選取&#x200B;**[!UICONTROL 開始於]**、**[!UICONTROL 結束於]**，或&#x200B;**[!UICONTROL 固定日期]**。

   - 當您已選取&#x200B;**[!UICONTROL 開始於]**&#x200B;或&#x200B;**[!UICONTROL 結束於]**，您可以建置完整的運算式。例如：**[!UICONTROL 結束於]**&#x200B;**[!UICONTROL 今年]**&#x200B;**[!UICONTROL 加上]**`1`**[!UICONTROL 天]**。為運算式的個別部分選擇適當的值。

      - 選取目前的值。例如，**[!UICONTROL 目前的年份]**。
      - 選取選擇性額外計算的值。 例如，**[!UICONTROL 加]**。
      - 當您指定其他計算時，請指定一個值。例如，`1`。
      - 當您已指定其他計算時，請選取用於計算的時段。例如，**[!UICONTROL 天]**。

   - 選取&#x200B;**[!UICONTROL 固定日]**&#x200B;時，請指定固定日，或使用選擇器選取日。

1. 選取&#x200B;**[!UICONTROL 隱藏]**&#x200B;以隱藏遞延日期計算的詳細資料。


### 自訂運算式

自訂運算式選項可讓您透過建立自訂運算式來變更日期範圍，或者您可輸入算術公式。

![日期範圍自訂運算式](assets/date-range-custom-expression.png){zoomable="yes"}

1. 選取&#x200B;**[!UICONTROL 使用滾動日期]**。

1. 選取&#x200B;**[!UICONTROL 使用自訂運算式]**。

   當您選取&#x200B;**[!UICONTROL 使用自訂運算式]**&#x200B;時，會停用標準滾動日期範圍控制項。

1. 輸入[自訂運算式](#create-a-custom-expression)。

1. 使用&#x200B;**[!UICONTROL 日期預覽]**&#x200B;來驗證產生的日期範圍。

#### 建立自訂運算式

1. 輸入[日期參考](#date-references)。

1. 新增選用的[日期運運算元](#date-operators)，將日期移動至過去或未來。

您可以輸入包含多個運運算元的自訂運算式，例如`tm-11m-1d`。

#### 日期參考

下列表格列出了日期參考的範例。

| 日期參考 | 類型 | 說明 |
|----------------|--------------|----------------------------|
| `1/1/10` | 靜態日期 | 以 ISO 日期格式輸入 |
| `td` | 滾動日期 | 當天的開始 |
| `tw` | 滾動日期 | 本週的開始 |
| `tm` | 滾動日期 | 本月的開始 |
| `tq` | 滾動日期 | 本季的開始 |
| `ty` | 滾動日期 | 本年度的開始 |

#### 日期運算子

下列表格列出了日期運算子的範例。

| 日期運運算元 | 單位 | 說明 |
|----------------|---------|--------------------|
| `+6d` | 日 | 新增 6 天至「日期參考」 |
| `+1w` | 週 | 將一整週加入「日期參考」 |
| `-2m` | 月 | 從「日期參考」減去 2 個整月 |
| `-4q` | 季 | 從「日期參考」減去 4 個季數 |
| -`1y` | 年 | 從「日期參考」減去一年 |

#### 日期運算式

下列表格列出了日期運算式範例。

| 日期運算式 | 含義 |
|-----------------|--------------------------------------|
| `td` | 今天 |
| `td-1w` | 上週的第一天 |
| `tm-1d` | 前一個月的最後一天 |
| `td-52w` | 52 週前的同一天 |
| `tm-11m-1d` | 去年同一個月的最後一天 |
| `"2020-09-06"` | 特定日期，2020年9月9日 |



## 儲存格的日期範圍

可在工作表儲存格中指定日期範圍。使用&#x200B;**[!UICONTROL 儲存格的日期範圍]**&#x200B;選項，從選取的儲存格中選擇資料區塊的開始和結束日期。 當您選取&#x200B;**[!UICONTROL 從儲存格]**&#x200B;選項時，面板會顯示&#x200B;**[!UICONTROL 從]**&#x200B;到&#x200B;**[!UICONTROL 到]**&#x200B;欄位，您可以在其中輸入儲存格位置，或使用![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)挑選目前選取的儲存格。

![從儲存格工作表1！H4選取至工作表1！I4](./assets/date-range-from-cell.png){zoomable="yes"}


## 排除當天

選取&#x200B;**[!UICONTROL 排除當天]**&#x200B;以從選取的日期範圍排除當天。 當天會排除在用於定義日期範圍的所有模式之外：行事曆、滾動日期或自訂運算式。


## 有效的日期範圍

下列清單說明有效的日期範圍格式。

- 開始和結束日期必須為下列格式: YYYY-MM-DD

- 開始日期必須早於或等於結束日期。兩個日期都可以設在未來。

- 若使用滾動日期，開始日期必須為當天或過去。如果選取&#x200B;**[!UICONTROL 排除當天]**，則開始日期必須為過去。

- 您可以建立一個為未來設定的靜態日期範圍。例如，您可能需要為下週推出的行銷活動設定一個未來日期。這個選項可預先為活動建立活頁簿監控。

## 變更日期範圍

您可以編輯現有資料區塊的日期範圍。

1. 在資料區塊中選取儲存格。

- 在&#x200B;**[!UICONTROL 命令]**&#x200B;面板中選取&#x200B;**[!UICONTROL 編輯資料區塊]**，或
- 在&#x200B;**[!UICONTROL 快速編輯]**&#x200B;面板中選取&#x200B;**[!UICONTROL 日期範圍]**&#x200B;連結。

1. 使用任何可用的日期選取範圍選項來修改日期範圍。

1. 選取&#x200B;**[!UICONTROL 「套用」]**。

Report Builder 會將新的日期範圍套用至選取範圍中的所有資料區塊。

<!--
To change the date range of an existing data block, select Edit a data block or use the QUICK EDIT panel.

Use the following options to change a date range for a data block.

**Calendar**

 The Calendar allows you to create static or rolling dates using the following options:

- Date range field
- Calendar
- Preset drop-down menu
- Rolling date mode
- Customize expressions


**From cell**

The **[!UICONTROL From cell]** option allows you to reference dates entered in worksheet cells.

You have the option to exclude today on any selected date range.

 ![Report Builder Quick edit pane with calendar selected and Exclude today selected.](./assets/image17.png)

## Use the Calendar

When you use the **Calendar**, the date range field displays the current date range for the data block request. You can enter dates directly into the date range field or use a data range selection option.

### Date range field

To enter dates directly into the date range field

1. Click the date range field next to the calendar icon.

1. Enter start and end dates for your date range.

### Calendar

To select dates using the calendar

1. Click the calendar icon to display a monthly calendar.

1. Click a start date.

1. Click an end date.

To set a date range in reverse, click the end date first and then click the start date.

![Report Builder date range pane showing the calendar and the end date and the start date selected.](./assets/image18.png)

### Preset drop down menu

The preset drop-down menu includes a standard set of preset date ranges and date range components for a report suite that you saved or a report suite that was shared with you.

### Rolling dates

The rolling dates option allows you to select a date range using rolling dates.

1. Select **Use rolling dates**.

1. Select a rolling expression for your start and or end date.

    ![Report Builder date range pane showing Use rolling dates selected and the rolling expression.](./assets/image19.png)

    **Start of** — Allows you to select the beginning of a day, week, month, quarter, or year.

    **End of** — Allows you to select the end of a day, week, month, quarter, or year.

    **Fixed day** — Allows you to fix a start or end date while the other date is rolling.

1. Choose day, week, month, quarter, or year as the rolling period.

    ![Report Builder date range pane showing the current day selected.](./assets/image20.png)

1. Add or subtract days, weeks, months, quarters, or years from your rolling date.

    ![Report Builder date range pane showing the current day plus 14 days selected.](./assets/image21.png)

1. Click Next to define the data range.

    Use the date preview to confirm the resulting date range is the desired range.

### Custom expressions

The custom expression option allows you to change the date range by building a custom expression or you can enter an arithmetic formula.

1. Select **Use rolling dates**.

1. Select **Use custom expression**.

    When you select the **Use custom expression** option, the standard rolling date range controls are disabled.

    ![Select Use custom expression showing tm-1m to td-1d.](./assets/custom_expression.png)

1. Enter a custom expression.

    For a sample list of custom expressions, see **Date expressions**.

1. Use the date preview to verify the resulting date range is the desired range.

#### Create a custom expression

1. Enter a **Date reference**.

1. Add **Date operators** to move the date to the past or future.

You can enter a custom date expression that includes multiple operators, such as ```tm-11m-1d```.

#### Date references

The following table lists date reference examples.

| Date Reference | Type         | Description                |
|----------------|--------------|----------------------------|
| 1/1/10         | Static Date  | Entered in ISO Date format |
| td             | Rolling Date | Start of current day       |
| tw             | Rolling Date | Start of current week      |
| tm             | Rolling Date | Start of current month     |
| tq             | Rolling Date | Start of current quarter   |
| ty             | Rolling Date | Start of current year      |

#### Date operators

The following table lists date operator examples.

| Date Operators | Unit    | Description   |
|----------------|---------|--------------------|
| +6d            | Day     | Add 6 days to the Date Reference |
| +1w            | Week    | Add one full week to the Date Reference |
| -2m            | Month   | Subtract 2 full months to the Date Reference |
| -4q            | Quarter | Subtract 4 quarters to the Date Reference |
| -1y            | Year    | Subtract one year to the Date Reference |

#### Date expressions

The following table lists date expression examples.

| Date Expression | Meaning                              |
|-----------------|--------------------------------------|
| td-1w           | First day of last week               |
| tm-1d           | Last day of previous month           |
| td-52w          | Same day, 52 weeks ago               |
| tm-11m-1d       | Last day of the same month last year |
| "2020-09-06"    | Sept 9th, 2020                       |

## Date range from cell

The date range can be specified in worksheet cells. Use the **Date range from cell** option to choose the data block start and end date from selected cells. When you select the **From cell** option, the panel displays **From** and **To** fields where you can enter a cell location.

![Select From cell Sheet1!H4 to Sheet1!I4](./assets/image23.png)

## Exclude today

Choose the **Exclude today** option to exclude today from a selected date range. Choosing to include today may pull incomplete data for today.

When selected, the **Exclude today** option excludes the current day from all date range modes including calendar, rolling dates, or custom expressions.

## Valid date ranges

The following list describe valid date range formats.

- The start and end dates must be in the following format: YYYY-MM-DD

- The start date must be earlier to or equal to the end date. Both dates can be set to the future.

- When using rolling dates, the start date must be today or in the past. It must be in the past if **Exclude today** is checked.

- You can create a static date range set for the future. For example, you may need to set a future date for a marketing campaign launch next week. This option creates a workbook monitoring for a campaign ahead of time.

## Change the date range

You can edit the date range of an existing data block by selecting Edit data block in the COMMANDS panel or by selecting the date range link in the QUICK EDIT panel.

**Edit data block** — Allows you to edit multiple data block parameters, including date range, for a single data block.

**Quick Edit: Date range** — Allows you to edit the date range of one or more data blocks.

To edit the date range from the QUICK EDIT panel

1. Select cells within one or more data blocks in a worksheet.

1. Click the **Date range** link in the QUICK EDIT panel.

1. Select the date range using any of the date selection options.

1. Click **Apply**.


Report Builder applies the new date range to all data blocks in the selection.
-->