---
description: 分析工作區中的日期比較可讓您取用包含日期範圍的任何欄，並建立常用的日期比較，例如年與年、季與季、月與月等。
seo-description: 分析工作區中的日期比較可讓您取用包含日期範圍的任何欄，並建立常用的日期比較，例如年與年、季與季、月與月等。
seo-title: 日期比較
title: 日期比較
uuid: ef18f9d9-b6ad-4859-b7c9-9750ca0df519
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 日期比較

Analysis Workspace 中的「日期比較」可讓您挑選任何含日期範圍的欄，然後建立常用的日期比較，例如: 年與年、季與季、月與月等。

## 比較時段 {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

分析需要內容，而通常這個內容是由先前的時段提供。例如，「我們的表現比去年的這個時候好/壞多少?」是您的公司要了解的基本問題。「日期比較」會自動包含「差異」欄，顯示與指定時段比較的百分比變更。

1. 建立自由表格，加入您要用時段比較的任何維度和量度。
1. Right-click a table row and select **[!UICONTROL Compare Time Periods]**.

   ![](assets/compare-time.png)

   >[!IMPORTANT]
   >
   >度量行、日期範圍行和時間維度行會停用此按滑鼠右鍵選項。

1. 您有以下這些比較選項，取決於您如何設定表格的日期範圍:

   | 選項 | 說明 |
   |---|---|
   | **[!UICONTROL 此日期範圍的前一週/月/季/年]** | 與此日期範圍的前一週/月/等比較。 |
   | **[!UICONTROL 去年本週/月/季/年]** | 與一年前的相同日期範圍比較。 |
   | **[!UICONTROL 選取範圍]** | 讓您選取自訂的日期範圍。 |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Select range]**.

1. 比較結果看起來像這樣:

   ![](assets/compare-time-result.png)

   「變化百分比」欄中的列呈紅色表示負值，綠色表示正值。

1. (可選) 如同任何其他 Workspace 專案，您可以根據這些時間比較建立視覺效果。例如，這張長條圖:

   ![](assets/compare-time-barchart.png)

   請注意，為了在長條圖中顯示變化百分比，您必須選取「[!UICONTROL 視覺效果設定]」中的「[!UICONTROL 百分比]」設定。

## Add a time period column for comparison {#section_93CC2B4F48504125BEC104046A32EB93}

您現在可以在表格的每個欄中新增時段，以新增不同於行事曆設定的時段。這是另一種比較日期的方式。

1. 以滑鼠右鍵按一下表格中的一欄，然後選取「**[!UICONTROL 新增時段欄」]**![](assets/add-time-period-column.png)

1. 您有以下這些比較選項，取決於您如何設定表格的日期範圍:

   | 選項 | 說明 |
   |---|---|
   | **[!UICONTROL 此日期範圍的前一週/月/季/年]** | 新增此日期範圍的前一週/月/等欄。 |
   | **[!UICONTROL 去年本週/月/季/年]** | 新增一年前的相同日期範圍。 |
   | **[!UICONTROL 選取範圍]** | 讓您選取自訂的日期範圍。 |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Select range]**.

1. 此時段會插入在您選取的欄之上:

   ![](assets/add-time-period-column2.png)

1. 您可以新增任意數目的欄，以及混合及比對不同日期範圍:

   ![](assets/add-time-period-column4.png)

1. 此外，您可以排序各欄，這會變更天數的次序，取決於您排序的欄。

## Align column dates to start on same row {#section_5085E200082048CB899C3F355062A733}

A new setting for all tables lets you **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**. 「套用至整個表格」的意思是，舉例來說，如果您劃分表格，並且變更劃分的某項設定，則會變更整個表格的該項設定。

![](assets/date-comparison-setting.png)

>[!IMPORTANT]
>
>This setting is **disabled** (unchecked) for all existing projects and **enabled** (checked) for all new projects.

範例: 當您選擇對齊日期，如果您進行 2016 年 10 月和 9 月間的月對月比較，左欄將從 10 月 1 日開始，右欄將從 9 月 1 日開始:

![](assets/add-time-period-column3.png)

<!-- 

<p>See Jonny Moon's email from November 3. </p>

 -->

