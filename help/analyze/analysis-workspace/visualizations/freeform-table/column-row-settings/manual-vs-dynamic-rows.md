---
title: 自由表格中的動態與靜態維度項目
description: 如何與表格中的動態和靜態維度項目互動。
feature: Freeform Tables
role: User, Admin
exl-id: 4cdc93b5-67ed-46a4-ba9f-a96e640da9d9
source-git-commit: 7f5fca4f7c3641d47e5d1d929a196d5e380c1e6b
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 90%

---

# 自由表格中的動態與靜態維度項目

在自由表格中，列和欄可以包含各種元件值。這些值可以是動態 (隨時間變動) 或靜態 (不隨時間變動)，視您要建立的分析而定。

## 動態維度項目

動態維度項目會隨時間變更，取決於依據自由表格中的哪個量度排序。分析特定時段排名最前的項目時，偏好使用動態維度項目。

將維度放入自由表格中時，會傳回動態列。它們代表對應至指定量度和時段之維度的排名最前項目。您也可以將維度放入自由表格欄中，維度會自動展開至排名前 5 的維度項目。

例如，將「瀏覽器類型」維度拖曳至表格時，頂端的「瀏覽器類型」維度項目 (例如 Microsoft、Apple、Google 等)會以動態方式傳回表格列。如果放入欄中，排名前 5 的「瀏覽器類型」維度項目會以動態方式傳回。

動態維度項目具有列篩選選項和X圖示，且確實如此 **not** 有鎖表徵圖。 <!--do they have the lock icon? --> 按一下動態維度項目旁的x時，會自動套用篩選器。 如需將篩選器套用至表格的詳細資訊，請參閱 [篩選及排序表格](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).

![](assets/dynamic-items.png)

## 靜態維度項目

靜態維度項目不會隨時間改變；它們是固定元件，一律會在自由表格中傳回。想要一律分析相同項目時，偏好使用靜態維度項目，不論該項目是特定行銷活動或一週中的特定幾天皆然。

每當您手動選取特定元件值 (維度、量度、區段、日期範圍) 並放入表格時，結果會是列或欄的靜態清單。如果選擇以下項目，也可以建立靜態量度項目：

* 在列中，按一下右鍵 >[!UICONTROL 「只顯示選取的列」]
* 在欄中，按一下滑鼠右鍵>[!UICONTROL 「將項目設為靜態」]

例如，拖曳至特定的「瀏覽器類型」項目 (例如 Microsoft 和 Apple) 時，這 2 個特定項目一律會被提取至表格中。

靜態維度項目&#x200B;**沒有**&#x200B;列篩選選項。而是每個項目都會顯示鎖定和 X 圖示。按一下 X 圖示即可從表格中刪除該維度項目。

![](assets/static-items.png)

## 混合維度項目

可以將來自不同維度的維度項目新增至相同的表格。在這類情況下，列標題會顯示「混合維度」。這些維度項目為靜態。例如，新增來自「瀏覽器類型」維度的特定維度項目，而其他維度項目來自「瀏覽器」維度。

![](assets/mixed-dimensions.png)

## 自由表格總計列

自由表格總計列中動態和靜態列的行為不相同。根據預設：

* 動態列會在伺服器端加總，並去除重複量度，例如造訪或訪客
* 靜態列則在用戶端加總，且&#x200B;**不會**&#x200B;去除重複量度。若要在伺服器端計算總計列，請將「列」設定更改為&#x200B;**「顯示總計」**。[了解更多](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=zh-Hant)

## 重新排序靜態資料列

以下是有關該主題的影片：

>[!VIDEO](https://video.tv.adobe.com/v/31319/?quality=12)
