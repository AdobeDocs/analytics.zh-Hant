---
title: 分析受事件影響的資料
description: 瞭解受事件影響的資料對整體資料品質的貢獻。
translation-type: tm+mt
source-git-commit: dfc2e036711ee2229160f52ab16fb4299f7722e5

---


# 分析受事件影響的資料

有時候，事件會影響組織中的資料品質。 例如：

* 傳送異常值資料的機器人，例如數百萬美元的收入
* 您的組織推送更新至您的網站，對您的Analytics實作造成負面影響
* 影響資料質量或完整性的其他問題

如果您的網站遇到資料品質問題、實作問題或資料中的其他差距，您可能會想要將其排除在報告之外，以免對部分資料做出決策。 使用這些區段來評估事件對您資料的影響，並決定您要如何進行。

## 使用區段分析並排除資料

Adobe Analytics提供簡單而強穩的方式，讓您使用區隔來關注或排除資料。 您可以使用區段中的日期範圍維度來篩選掉或關注這些特定日期。 請參 [閱「元件」使用指南中](/help/components/c-segmentation/use-cases/exclude-date-range.md) 「分析中排除特定日期」。

## 比較事件與先前的日期範圍

如果您想要進一步瞭解某個事件對您的資料隨著時間而產生的影響，可以在分析工作區中使用日期比較。 此功能可讓您逐日、逐周或逐月比較資料，以檢視其與先前範圍的比較。 然後，您可以使用此比較來判斷事件對趨勢的影響程度。 請參 [閱「分析使用指南」中的「比較受事件影響的日期](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) 」與先前範圍。

## 使用計算量度修正趨勢資料

建立區段並使用日期比較後，您就可以結合這兩個概念，使用計算度量來修正趨勢資料。 在計算量度中納入區段，然後將受影響的日期乘以比較日期時發現的偏移。 請參 [閱「元件」使用指南中](/help/components/c-calcmetrics/cm-events.md) 「衍生受事件影響的資料」。

## 在「報告與分析」中使用日曆事件

如果您使用「報告與分析」，則可使用日曆事 [件](/help/components/t-calendar-event.md) ，在任何趨勢報表中反白標示受影響的日。 此方法不適用於分析工作區。

1. 導覽至 **[!UICONTROL Components]** > **[!UICONTROL Calendar events]**。
2. 輸入所要的標題、日期範圍和附註文字。
3. 按一下 **[!UICONTROL Save]**.

![日曆事件](assets/exclude_calendar_event.jpg)
