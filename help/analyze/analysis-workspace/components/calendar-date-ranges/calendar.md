---
description: 使用日曆和資料範圍來指定 Analysis Workspave 中的日期範圍。
title: 日期範圍概觀
feature: Date Ranges
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: ht
source-wordcount: '532'
ht-degree: 100%

---


# 日期範圍概觀

在 Workspace 專案中，您通常會使用[面板中的行事曆](/help/analyze/analysis-workspace/c-panels/panels.md#calendar)來指定該面板中視覺效果的日期範圍。

日期範圍元件可讓您定義和覆蓋面板的行事曆設定。


## 使用日期範圍

您可以使用日期範圍元件來重新定義面板的行事曆。

或者，您可以使用自由格式表中的日期範圍作為量度或維度。

![日期範圍使用](assets/date-ranges-usage.png)

- **量度**。 例如，比較兩個不同月份特定量度的維度。
- **維度**。 比較日期範圍維度上的不同維度項目量度。

>[!NOTE]
>
>當您在自由格式表中使用日期範圍時，日期範圍會覆寫自由格式表所屬面板指定的行事曆。
>

使用日期範圍的方式與[使用任何元件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md#analysis-workspace-components)的方式一樣。您從![行事曆](/help/assets/icons/Calendar.svg) **[!UICONTROL 日期範圍]** 元件面板將日期範圍拖曳到：

- **[!UICONTROL 行事曆]**：您使用日期範圍![切換](/help/assets/icons/Switch.svg) **[!UICONTROL 取代]**&#x200B;目前的行事曆設定。
- **量度欄標題**：您![切換](/help/assets/icons/Switch.svg) **[!UICONTROL 取代]**&#x200B;量度，![新增](/help/assets/icons/Add.svg)**[!UICONTROL 新增&#x200B;]**日期範圍作為量度，或使用日期範圍元件來![篩選](/help/assets/icons/Filter.svg)**[!UICONTROL &#x200B;篩選&#x200B;]**量度。
- **維度欄標題**：您![切換](/help/assets/icons/Switch.svg) **[!UICONTROL 取代]**&#x200B;目前的維度。現在的新維度是&#x200B;**[!UICONTROL 日期範圍]**。只要維度是日期範圍，您就可以![新增](/help/assets/icons/Add.svg)**[!UICONTROL 新增&#x200B;]**其他日期範圍作為維度項目。
- **維度項目**：您可依日期範圍![劃分](/help/assets/icons/Breakdown.svg) **[!UICONTROL 劃分]**&#x200B;特定維度項目。

您也可以直接在自由格式表格視覺效果中新增日期範圍欄：

1. 在量度欄中，從內容選單中選取：

   - **[!UICONTROL 新增時段欄]**。您可以在根據目前行事曆的建議選項中選取，或建立[自訂日期範圍](#custom-date-ranges)。
   - **[!UICONTROL 比較時段]**。 您可以在根據目前行事曆的建議選項中選取，或建立[自訂日期範圍](#custom-date-ranges)。

1. 根據您的選擇，額外的日期範圍欄將會新增至自由格式表中。

## 預設日期範圍

Analysis Workspace 提供許多預設的日期範圍。


| 日 | 週 | 月 | 季 | 年 |
|---|---|---|---|---|
| 今天 | 本週 | 本月 | 本季度 | 今年 |
| 昨天 | 本週 (不含今天) | 本月 (不含今天) | 本季 (不含今天) | 今年 (不含今天) |
| 2 天前 | 2 週前 | 2 個月前 |   |  |
| 3 天前 | 3 週前 | 3 個月前 |  | |
| 最近 7 天 | 上週 | 上個月 | 上一季 | 去年 |
| 最近 14 天 | 過去完整 2 週 | 過去 2 個月整 | 過去完整 4 季 | |
| 最近 30 天 | 過去完整 3 週 | 過去 3 個月整 | | |
| 最近 60 天 | 過去完整 4 週 | 過去 6 個月整 | | |
| 最近 90 天 | 過去完整 12 週 | 過去 12 個月整 | | |
| 過去完整 7 天 | 過去完整 52 週 | 過去 13 個月整 | | |
| 過去完整 14 天 | | | | |
| 過去完整 30 天 | | | | |
| 過去完整 90 天 | | | | |

<table style="table-layout:fixed">

## 自訂日期範圍

您可以建立專屬的自訂日期範圍。有關建立日期範圍時可使用的各種選項，請參閱[建立日期範圍](create.md)。然後，您可以在[日期範圍產生器](create.md#date-range-builder)中建立、修改和儲存日期範圍。

您可以使用[日期範圍管理器](manage.md)來管理日期範圍。



<!--
# Calendar and date ranges overview {#date-range}

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="End time"
>abstract="End times always include 59 seconds."



In the calendar, you can specify dates and date ranges, or select a preset.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calendar and date ranges overview](https://video.tv.adobe.com/v/23973?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


Calendar selections apply at the panel level, but you have the option to apply them to all panels. When you click a date range in Workspace, the interface displays the current calendar month and the previous calendar month. You can adjust these two calendars by clicking the right and left arrows in each respective upper corner.

![Calendar](assets/aw_calendar2.png){width="60%"} 

## Select and apply date ranges {#select-apply}

The first click on a calendar starts a date range selection. The second click completes a date range selection, which becomes highlighted. If the `Shift` key is held down (or right-click is used), it appends to the currently selected range.

You can also drag dates (and time dimensions) into a Workspace project. You can select specific days, weeks, months, years, or a rolling date.

[Using Date Ranges and Calendar in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=zh-Hant) (4:07)

| Setting | Description |
|--- |--- |
|Selected Days|Selected days/weeks/months/years.|
|Make date range components relative to panel calendar| If disabled, any date range components used within a table, visualization, or panel drop zone override the panel calendar. <p>If enabled, any date range components used within a table, visualization, or panel drop zone are in relation to the panel date range. For example, if the panel date range is set to November 1 through November 30, and a Last Week date range component is used in a freeform table, the information in the freeform table refers to the last week in October. |
|Use rolling dates| Rolling dates allow you to generate a dynamic report that looks forward or backward for a set period of time based on when you ran the report. For example, if you want to report on all Orders placed "Last Month" (based on the Created Date field) and ran that report in December, you'd see orders placed in November. If you ran that same report in January, you'd see orders placed in December.<ul><li>**[!UICONTROL Date Preview]**: Indicates what time period the rolling calendar encompasses.</li><li>**[!UICONTROL Start]**: You can choose among current day, current week, current month, current quarter, current year.</li><li>**[!UICONTROL End]**: You can choose among current day, current week, current month, current quarter, current year.</li></ul>To view an example, see [Custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). <br>Selected by default.|
|Date Range|Lets you pick a preset date range. Last 30 days is the default. **[!UICONTROL This week/month/quarter/year (excluding today)]** lets you choose from date ranges that do not include partial-day data from today.|
|Apply to All Panels|Lets you not only change the selected date range for the current panel, but also for all other panels within the project.|
|Apply|Applies the date range to this panel only.|

## About relative panel date ranges {#relative-panel-dates}

If you're working in Workspace, you can make the date range components relative to the panel calendar. 
Three common use cases where you'll see relative panel dates take effect are Combo charts, Key metrics summary, and Freeform table date ranges.

To use relative panel date ranges

1. Select the **Workspace** tab.
1. Select **Blank project**.
1. Add dimensions, metrics, and segments from the left rail. 
1. Click the panel date range field to toggle the relative panel date range setting.
1. Select **Make date range components relative to panel calendar**.
    * Select the option to make the date range components relative to the panel calendar.
        If relative dates are selected, then rolling dates will be based on the start date of the panel calendar and not today's date.
    * If this option isn't selected, then rolling dates will be based on today's date.

    ![relative panel dates](assets/relative-date-selected.png){width="60%"} 

1. Click **Apply**.
    The relative dates are shown in the upper-right.

    ![relative dates in freeform ](assets/relative-date-range1.png)

## Guidelines for relative panel date ranges {#guidelines}

Keep in mind the following guidelines when using relative panel date ranges.

### Formulas and relative date ranges {#formula-relative-dates}

If you have relative dates selected, all date formulas will use the panel's start date as the starting point.

### Custom calendars and relative date ranges {#custom-calendar-formulas}

When you use a week-based custom calendar and you add months or years, the formula calculates the offset of the day in the given period. The actual date may be different because of the offset. The formula chooses the day landing in the same place in the custom calendar. For example, the third Friday of the third week in a custom calendar.

### About segments that use rolling dates and relative panel date ranges {#segments-relative-dates}

If you build a segment or use a segment with a rolling date, for example, the Last 7 Days or the Last 2 Weeks, and you click on the segment preview, it will start the rolling date from *Today* instead of the panel start date. As a result the preview for the segment will not match when you actually use the segment in the table. The preview is impacted, not the segment itself. 

## Guidelines for panel date ranges and previews {#guidelines-panel-dates}

* Starting with the February release, component and data previews will be based on the panel date range and not the last 90 days. 
* All components listed in the left rail will be available based on the panel date range. 
* All date previews in the segment and calculated metric builders will be based on the panel date range (unless accessed from the component managers, which do not have an associated panel, they will still be based on the last 90 days). 
* Any data previews will display data or components based on the panel date range.

-->