---
description: 瞭解如何將標準和有限的格式套用至儲存格範圍。
title: 如何以Report Builder格式化日期
uuid: 5211db30-07b3-4413-97c3-e40e6ff223cd
feature: Report Builder
role: User, Admin
exl-id: 9b251b09-9156-40b5-8e1f-fb6594a25c26
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 81%

---

# 格式化日期

{{legacy-arb}}

除了可透過Excel的「格式>儲存格(Ctrl+1)」功能使用的標準儲存格格式選項外，您還可以將有限的格式套用至具有Report Builder的儲存格範圍。 這些格式選擇取決於您選擇的度量。

[新增維度](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)至「列標籤」格線後，請按一下&#x200B;**[!UICONTROL 「格式」]**。

在「**[!UICONTROL 格式]**」功能表中按一下「**[!UICONTROL 自訂格式]**」以套用日期的自訂格式，其形式與在開頭和結尾附加文字的功能相似。例如，您可以輸入一律要出現日期後的文字 (如 A.D. B.C.E. A.H. 等)。您可以在日期前加上文字，如「[!UICONTROL 開始日期]」和「[!UICONTROL 開始與結束日期]」。除此之外，您還可以利用日、月、年等縮寫建構自訂日期運算式，以及在日期的各個部分間使用自訂分隔符號。所有日期格式都只能由三個以方括號包覆的縮寫組成。

下表說明如何在[!UICONTROL 「自訂格式」]欄位中使用日期縮寫：

| 縮寫 | 含義 | 範例   使用2012年3月14日星期三 |
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
