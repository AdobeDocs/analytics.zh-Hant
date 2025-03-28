---
description: Analysis Workspace 中的「日期比較」可讓您挑選任何含日期範圍的欄，然後建立常用的日期比較，例如：逐年比較、逐季比較、逐月比較等。
title: 日期比較
feature: Calendar
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: ht
source-wordcount: '747'
ht-degree: 100%

---

# 日期比較

Analysis Workspace 中的「日期比較」可讓您挑選任何含日期範圍的欄，然後建立常用的日期比較，例如：年與年、季與季、月與月等。


>[!BEGINSHADEBOX]

請參閱 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [日期比較](https://video.tv.adobe.com/v/30753?quality=12&learn=on){target="_blank"}的示範影片。

>[!ENDSHADEBOX]



## 比較時段 {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>[!UICONTROL 比較時段]會使用進階計算量度。因此，它僅適用於擁有 Analytics Select、Prime 和 Ultimate SKU 的客戶。

分析所需內容，而通常這個內容是由先前的時段提供。例如，「我們的表現比去年的這個時候好或壞多少？」是您的公司要了解的基本問題。「日期比較」會自動加入「差異」欄，在當中顯示與特定時段相較之下的百分比變化。

1. 建立自由表格，加入您要用時段比較的任何維度和量度。
1. 以滑鼠右鍵按一下表格列，然後選取「**[!UICONTROL 比較時段]**」。

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >這個右鍵選項不適用於量度列、日期範圍列和時間維度列。

1. 您有以下這些比較選項，取決於您如何設定表格的日期範圍：

   | 選項 | 說明 |
   |---|---|
   | **[!UICONTROL 此日期範圍的前一週/月/季/年]** | 與此日期範圍的前一週/月/等比較。 |
   | **[!UICONTROL 此日期範圍的當週/月/季/年/去年]** | 與一年前的相同日期範圍比較。 |
   | **[!UICONTROL 將日期範圍自訂為此日期範圍]** | 可讓您選取自訂的日期範圍。 |

   >[!NOTE]
   >
   >如果您選取自訂天數，例如 10 月 7 日至 10 月 20 日 (14 天的範圍)，您將僅有 2 個選項：「**[!UICONTROL 此日期範圍的前 14 天]**」和「**[!UICONTROL 將日期範圍自訂為此日期範圍]**」。

1. 比較結果看起來像這樣：

   ![](assets/compare-time-result.png)

   「變化百分比」欄中的列呈紅色表示負值，綠色表示正值。

1. (選用) 如同任何其他 Workspace 專案，您可以根據這些時間比較建立視覺效果。例如，這張長條圖：

   ![](assets/compare-time-barchart.png)

   請注意，為了在長條圖中顯示變化百分比，您必須選取「[!UICONTROL 視覺效果設定]」中的「[!UICONTROL 百分比]」設定。

## 新增時段欄以進行比較 {#section_93CC2B4F48504125BEC104046A32EB93}

您現在可以在表格的每個欄中新增時段，以新增不同於行事曆設定的時段。這是另一種比較日期的方式。

1. 以滑鼠右鍵按一下表格中的一欄，然後選取「**[!UICONTROL 新增時段欄]**」。

   ![](assets/add-time-period-column.png)

1. 您有以下這些比較選項，取決於您如何設定表格的日期範圍：

   | 選項 | 說明 |
   |---|---|
   | **[!UICONTROL 此日期範圍的前一週/月/季/年]** | 新增此日期範圍的前一週/月/等欄。 |
   | **[!UICONTROL 此日期範圍的當週/月/季/年/去年]** | 新增一年前的相同日期範圍。 |
   | **[!UICONTROL 將日期範圍自訂為此日期範圍]** | 可讓您選取自訂的日期範圍。 |

   >[!NOTE]
   >
   >如果您選取自訂天數，例如 10 月 7 日至 10 月 20 日 (14 天的範圍)，您將僅有 2 個選項：「**[!UICONTROL 此日期範圍的前 14 天]**」和「**[!UICONTROL 將日期範圍自訂為此日期範圍]**」。

1. 此時段會插入在您選取的欄之上：

   ![](assets/add-time-period-column2.png)

1. 您可以新增任意數目的欄，以及混合及比對不同日期範圍：

   ![](assets/add-time-period-column4.png)

1. 此外，您可以排序各欄，這會變更天數的次序，取決於您排序的欄。

## 對齊欄日期讓開始日期在同一列 {#section_5085E200082048CB899C3F355062A733}

您可以讓每一欄的日期與同一列中所有開始日期一致。

例如，當您選擇對齊日期，如果您進行 2016 年 10 月和 9 月間的月對月比較，左欄將從 10 月 1 日開始，右欄將從 9 月 1 日開始：

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>使用此選項時請考慮下列事項：
>
>* 所有新項目均根據預設啟用此設定。
>
>* 此設定套用至整個表格。例如，如果您變更表格內劃分的設定，將變更整個表格的設定。
>

若尚未啟用此設定，請進行啟用：

1. 在您想要對齊欄日期的表格中，選取表格標題中的「**設定**」圖示。

1. 在&#x200B;[!UICONTROL **設定**]&#x200B;索引標籤，選取「**[!UICONTROL 對齊各欄日期，讓所有開始日期在同一列 (套用至整個表格)]**」。

![](assets/date-comparison-setting.png)


