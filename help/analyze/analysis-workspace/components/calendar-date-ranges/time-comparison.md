---
description: Analysis Workspace 中的「日期比較」可讓您挑選任何含日期範圍的欄，然後建立常用的日期比較，例如：逐年比較、逐季比較、逐月比較等。
title: 日期比較
uuid: ef18f9d9-b6ad-4859-b7c9-9750ca0df519
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 日期比較

Analysis Workspace 中的「日期比較」可讓您挑選任何含日期範圍的欄，然後建立常用的日期比較，例如：年與年、季與季、月與月等。

## 比較時段 {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

分析需要內容，而通常這個內容是由先前的時段提供。例如，「我們的表現比去年的這個時候好/壞多少？」是您的公司要了解的基本問題。「日期比較」會自動加入「差異」欄，在當中顯示與特定時段相較之下的百分比變化。

1. 建立自由表格，加入您要用時段比較的任何維度和量度。
1. 按一下右鍵表行並選擇 **[!UICONTROL Compare Time Periods]**。

   ![](assets/compare-time.png)

   >[!IMPORTANT]
   >
   >這個右鍵選項不適用於量度列、日期範圍列和時間維度列。

1. 您有以下這些比較選項，取決於您如何設定表格的日期範圍：

   | 選項 | 說明 |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | 與此日期範圍的前一週/月/等比較。 |
   | **[!UICONTROL This week/month/quarter/year last year]** | 與一年前的相同日期範圍比較。 |
   | **[!UICONTROL Select range]** | 讓您選取自訂的日期範圍。 |

   >[!NOTE]
   >
   >當您選取自訂的天數（例如10月7日- 10月20日）（14天範圍）時，您只會得到2個選項： **[!UICONTROL Prior 14 days before this date range]**&#x200B;和 **[!UICONTROL Select range]**。

1. 比較結果看起來像這樣：

   ![](assets/compare-time-result.png)

   「變化百分比」欄中的列呈紅色表示負值，綠色表示正值。

1. (選用) 如同任何其他 Workspace 專案，您可以根據這些時間比較建立視覺效果。例如，這張長條圖：

   ![](assets/compare-time-barchart.png)

   Note that in order to show the percentage change in the bar chart, you have to have the [!UICONTROL Percentages] setting checked in the [!UICONTROL Visualization Settings].

## 新增時段欄以進行比較 {#section_93CC2B4F48504125BEC104046A32EB93}

您現在可以在表格的每個欄中新增時段，以新增不同於行事曆設定的時段。這是另一種比較日期的方式。

1. 按一下右鍵表中的列並選擇 **[!UICONTROL Add Time Period Column]**![](assets/add-time-period-column.png)

1. 您有以下這些比較選項，取決於您如何設定表格的日期範圍：

   | 選項 | 說明 |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | 新增此日期範圍的前一週/月/等欄。 |
   | **[!UICONTROL This week/month/quarter/year last year]** | 新增一年前的相同日期範圍。 |
   | **[!UICONTROL Select range]** | 讓您選取自訂的日期範圍。 |

   >[!NOTE]
   >
   >當您選取自訂的天數（例如10月7日- 10月20日）（14天範圍）時，您只會得到2個選項： **[!UICONTROL Prior 14 days before this date range]**&#x200B;和 **[!UICONTROL Select range]**。

1. 此時段會插入在您選取的欄之上：

   ![](assets/add-time-period-column2.png)

1. 您可以新增任意數目的欄，以及混合及比對不同日期範圍：

   ![](assets/add-time-period-column4.png)

1. 此外，您可以排序各欄，這會變更天數的次序，取決於您排序的欄。

## 對齊欄日期讓開始日期在同一列 {#section_5085E200082048CB899C3F355062A733}

所有表格的新設定都可讓您使用 **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**。 「套用至整個表格」的意思是，舉例來說，如果您劃分表格，並且變更劃分的某項設定，則會變更整個表格的該項設定。

![](assets/date-comparison-setting.png)

>[!IMPORTANT]
>
>此設定針對所有現有專案設為&#x200B;**「停用」**(未勾選)，針對所有新專案則設為&#x200B;**「啟用」**(已勾選)。

範例：當您選擇對齊日期，如果您進行 2016 年 10 月和 9 月間的月對月比較，左欄將從 10 月 1 日開始，右欄將從 9 月 1 日開始：

![](assets/add-time-period-column3.png)

<!-- 

<p>See Jonny Moon's email from November 3. </p>

 -->

