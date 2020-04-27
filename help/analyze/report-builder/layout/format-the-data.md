---
description: 除了 Excel「格式 > 儲存格」(Ctrl+1) 功能提供的標準儲存格格式選擇之外，您還可以透過 Report Builder 將有限的格式套用至儲存格範圍。這些格式選擇取決於您選擇的度量。
title: 日期格式
topic: Report builder
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 日期格式

除了 Excel「格式 > 儲存格」(Ctrl+1) 功能提供的標準儲存格格式選擇之外，您還可以透過 Report Builder 將有限的格式套用至儲存格範圍。這些格式選擇取決於您選擇的度量。

After you [add dimensions](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) to the Row Labels grid, click **[!UICONTROL Format]**.

In the **[!UICONTROL Format]** menu, click **[!UICONTROL Custom Format]** to apply customized formats for dates similar to the prepend and postpend feature. 例如，您可以輸入一律要出現日期後的文字 (如 A.D. B.C.E. A.H. 等)。您可以在日期之前新增文字，例如 [!UICONTROL Start Date] 和 [!UICONTROL Start and End Date]。 除此之外，您還可以利用日、月、年等縮寫建構自訂日期運算式，以及在日期的各個部分間使用自訂分隔符號。所有日期格式都只能由三個以方括號包覆的縮寫組成。

The following table describes how you can use date abbreviations in the [!UICONTROL Custom Format] field:

| 縮寫 | 含義 | 範例使用 2012 年 3 月 14 日星期三 |
|--- |--- |--- |
| MM/dd/yyy | 完整的數值日期 | 2012/03/14 |
| M | 月份的數值 | 3 |
| MM | 月份的數值，小於 10 的月需補上 0 | 03 |
| MMM | 月份的簡短名稱 | 3月 |
| MMMM | 月份的完整名稱 | 3 月 |
| D | 完整日期 | 2012 年 3 月 14 日星期三 |
| d | 日的數值 | 14 |
| dd | 日的數值，小於 10 的日需補上 0 | 01 – 09 |
| ddd | 日的簡短名稱 | 週三 |
| dddd | 日的完整名稱 | 星期三 |
| yy | 2 位數的年份 | 10 |
| yyyy | 4 位數的完整年份 | 2012 |
