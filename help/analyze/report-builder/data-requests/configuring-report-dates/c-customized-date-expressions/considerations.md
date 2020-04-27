---
description: '使用「自訂運算式」設定日期範圍時，有兩項重要事項需要考量： '
title: 自訂日期考量事項
topic: Report builder
uuid: a3bb3a63-0f15-4292-ade7-4ea852fe68c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 自訂日期考量事項

使用自訂運算式設定日期範圍時，有兩項重要事項需要考量：

* 報表的執行日期 (截止日期，或請求的重新整理日期) 決定可用的資料為何。
* 報表的開始日期和結束日期變換會影響報表涵蓋的日期範圍。

由於資料的可用性會隨著報表的時間範圍和在報表中重新整理請求的日期而改變，因此請務必在適當的日期執行報表，以便擷取所需的資訊。以下範例是上述兩項考量事項的示範。

Assume you make a request for [!UICONTROL Page Views] using Aggregated granularity. 在北美洲，一週的開始為星期日。若要取得星期日到星期六這段期間的更新報表 (例如，2008 年 11 月 23 日到 11 月 29 日)，請在星期日 (11 月 30 日) 執行報表 (重新整理請求)，以取得前一週 (11/23 到 11/29) 的資料。

使用此自訂運算式：

*開始日期:* cw-1w *結束日期:* cw-1d

An analysis of the customize expression when the inclusive [!UICONTROL End Date] for the request is 11/30:

*開始日期:* cw-1w

目前這週的開始 (11 月 30 日星期日) 減去七天 = 上一週的開始 (11 月 23 日星期日)

*結束日期:* cw-1d

目前這週的開始 (11 月 30 日星期日) 減去一天 = 11 月 29 日星期六

After the customized expression is mapped to the spreadsheet, refresh the request using Sunday, November 30, 2008 as the inclusive [!UICONTROL End Date] for the floating request. 資料會反應這一週內的情況。

If instead you refresh the expression and specify Saturday, November 29 as the [!UICONTROL End Date] for the floating request, the data will reflect the week 11/16 to 11/22. 這是因為重新整理請求的參考日期提早了一天。

Here are the differences when the inclusive [!UICONTROL End Date] for the request is 11/29:

*開始日期:* cw-1w

目前這週的開始 (11 月 23 日星期日) 減去七天 = 上一週的開始 (11 月 16 日星期日)

*結束日期:* cw-1d

目前這週的開始 (11 月 23 日星期日) 減去一天 = 11 月 22 日星期六

在歐洲和其他某些國家/地區，一週的開始為星期一，而非星期日。在這種情況下，您可以自訂日曆來變更開始日期(請參閱 [自訂日曆](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)。)
