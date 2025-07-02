---
description: 瞭解如何在Analysis Workspace中使用日期比較，其可讓您挑選任何包含日期範圍的欄，並建立常用的日期比較。
title: 日期比較
feature: Date Ranges
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: 3d15bd941cb8eaf20b8ae9f1ffa1dbfd403b2bfa
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 35%

---

# 日期比較

Analysis Workspace中的日期比較可讓您挑選任何含日期範圍的欄，然後建立常用的日期比較，例如：逐年比較、逐季比較、逐月比較等。

## 比較時段

分析所需內容，而通常這個內容是由先前的時段提供。例如，問題&#x200B;*您現在的表現與去年的這個時候相較之下，有好多少壞？*&#x200B;是瞭解您業務的基礎。 日期比較會自動包含&#x200B;*差異*&#x200B;欄，顯示與指定時段相比的百分比變化。

1. 建立[自由表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)，其中包含您要用時段比較的任何維度和量度。
1. 開啟表格列的內容功能表，並選取&#x200B;**[!UICONTROL 比較時段]**。

   ![已選取比較時段的表格列](assets/compare-time.png)

   >[!NOTE]
   >
   >此內容功能表選項不適用於量度列、日期範圍列和時間維度列。

1. 您有以下這些比較選項，取決於您如何設定表格的日期範圍：

   | 選項 | 說明 |
   |---|---|
   | **[!UICONTROL 在此日期範圍之前&#x200B;*x*周/月/季/年]** | 與此日期範圍之前的所選日期範圍比較。 |
   | **[!UICONTROL 去年到此日期範圍的x周/月/季/年]** | 與一年前的相同日期範圍比較。 |
   | **[!UICONTROL 將日期範圍自訂為此日期範圍]** | 可讓您定義自訂日期範圍。 |

   >[!NOTE]
   >
   >如果您選取自訂天數，例如 10 月 7 日至 10 月 20 日 (14 天的範圍)，您將僅有 2 個選項：「**[!UICONTROL 此日期範圍的前 14 天]**」和「**[!UICONTROL 將日期範圍自訂為此日期範圍]**」。

1. 比較結果看起來像這樣：

   ![顯示日期範圍和百分比變更比較的自由格式表格。](assets/compare-time-result.png)

   「百分比變更」欄中的列在負值時顯示為紅色，在正值時顯示為綠色。

## 新增時段欄以進行比較

您現在可以在表格中的每一欄新增時段，讓您新增與行事曆所設定的時段不同的時段。

1. 以滑鼠右鍵按一下表格中的一欄，然後選取「**[!UICONTROL 新增時段欄]**」。

   ![](assets/add-time-period-column.png)

1. 您有以下這些比較選項，取決於您如何設定表格的日期範圍：

   | 選項 | 說明 |
   |---|---|
   | **[!UICONTROL 在此日期範圍之前&#x200B;*x*周/月/季/年]** | 新增包含周/月/等的欄 週/月/等比較。 |
   | **[!UICONTROL 去年至此日期範圍的這&#x200B;*x*周/月/季/年]** | 新增一年前的相同日期範圍。 |
   | **[!UICONTROL 將日期範圍自訂為此日期範圍]** | 可讓您建立自訂日期範圍。 |

   >[!NOTE]
   >
   >如果您選取自訂天數，例如 10 月 7 日至 10 月 20 日 (14 天的範圍)，您將僅有 2 個選項：「**[!UICONTROL 此日期範圍的前 14 天]**」和「**[!UICONTROL 將日期範圍自訂為此日期範圍]**」。

1. 此時段會插入在您選取的欄之上：

   ![自由格式表格，顯示目前行事曆期間和上一個行事曆月份的發生次數。](assets/add-time-period-column2.png)

1. 您可以新增任意數目的欄，以及混合及比對不同日期範圍：

1. 此外，您可以排序每一欄，這會根據您排序的欄變更天數順序。

## 對齊欄日期讓開始日期在同一列

您可以讓每一欄的日期與同一列中所有開始日期一致。

例如，您可對最後一週（截至2024年10月5日）與上一週進行逐日比較。 依預設，左欄將從9月22日開始，右欄將從9月29日開始。

![未對齊日期](assets/not-align-dates.png)

您可以在&#x200B;**[!UICONTROL 設定]**&#x200B;中為自由格式表格視覺效果啟用[對齊各欄日期，讓所有開始日期在同一列](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1)，讓欄日期在同一列開始。

![](assets/align-dates.png)

使用此選項時請考慮下列事項：

* 所有新項目均根據預設啟用此設定。

* 此設定套用至整個表格。例如，如果您變更表格中劃分的這項設定，該設定會套用至整個表格。


<!--
# Date comparison

Date comparison in Analysis Workspace lets you take any column containing a date range and create a common date comparison, such as: year-over-year, quarter-over-quarter, month-over-month, etc.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Date comparison](https://video.tv.adobe.com/v/30753?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



## Compare time periods {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>[!UICONTROL Compare Time Periods] leverages advanced Calculated Metrics. As a result, it is available only to customers with Analytics Select, Prime, and Ultimate SKUs. 

Analysis requires context, and often that context is provided by a previous time period. For example, the question "How much better or worse are we doing than at this time last year?" is fundamental to understanding your business. Date Comparison automatically include a "difference" column, which shows the percentage change compared to a specified time period.

1. Create a Freeform table, with any dimensions and metrics you want to compare over a time period.
1. Right-click a table row and select **[!UICONTROL Compare time periods]**.

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >This right-click option is disabled for metric rows, date range rows, and time dimension rows.

1. Depending on how you have set the table's date range, you have these options for comparison: 

   |  Option  | Description  |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Compares to the week/month/etc. immediately before this date range.  |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Compares to the same date range a year ago.  |
   | **[!UICONTROL Custom date range to this date range]** | Lets you select a custom date range.  |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Custom date range to this date range]**.

1. The resulting comparison looks like this:

   ![](assets/compare-time-result.png)

   Rows in the Percent Change column appear red for negative values and green for positive values.

1. (Optional) As in any other Workspace projects, you can create visualizations based on these time comparisons. For example, here is a Bar graph:

   ![](assets/compare-time-barchart.png)

   Note that in order to show the percentage change in the bar chart, you have to have the [!UICONTROL Percentages] setting checked in the [!UICONTROL Visualization Settings].

## Add a time period column for comparison {#section_93CC2B4F48504125BEC104046A32EB93}

You can now add a time period to each column in a table, enabling you to add a time period that is different from the one your calendar is set to. This is another way you can compare dates.

1. Right-click a column in the table and select **[!UICONTROL Add time period column]**. 

   ![](assets/add-time-period-column.png)

1. Depending on how you have set the table's date range, you have these options for comparison: 

   |  Option  | Description  |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Adds a column with the week/month/etc. immediately before this date range.  |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Adds the same date range a year ago.  |
   | **[!UICONTROL Custom date range to this date range]** | Lets you select a custom date range.  |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Custom date range to this date range]**.

1. The time period will be inserted on top of the column you selected:

   ![](assets/add-time-period-column2.png)

1. You can add as many time columns as you want, as well as mix and match different date ranges:

   ![](assets/add-time-period-column4.png)

1. In addition, you can sort on each column, which will change the order of days depending on the column you are sorting on.

## Align column dates to start on the same row {#section_5085E200082048CB899C3F355062A733}

You can align the dates from each column to all start on the same row. 

For example, when you choose to align the dates, if you do a month-over-month comparison between October and September 2016, the left column will start with October 1 and the right column will start with September 1:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Consider the following when using this option:
>
>* This setting is enabled by default for all new projects.
>
>* This setting applies to the entire table. For example, if you change this setting for a breakdown within the table, it will change the setting for the entire table.
>

To enable this setting, if it is not already enabled:

1. In the table where you want to align column dates, select the **Settings** icon in the table header.

1. On the [!UICONTROL **Settings**] tab, select **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**.

![](assets/date-comparison-setting.png)


-->