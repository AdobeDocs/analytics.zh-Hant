---
description: 顯示人們最常點擊連往您網站之外的連結。這些連結通常指向合作夥伴或附屬機構的網站。但是，也可能是您實作外部連結的任何位置。您可以使用這個報告來檢視最熱門的附屬機構連結，或者協助驗證您的合作夥伴發佈您提供轉接連結的數量。
title: 退出連結
topic: Reports
uuid: e1452f04-389d-4aa3-8763-732880284302
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 退出連結

顯示人們最常點擊連往您網站之外的連結。這些連結通常指向合作夥伴或附屬機構的網站。但是，也可能是您實作外部連結的任何位置。您可以使用這個報告來檢視最熱門的附屬機構連結，或者協助驗證您的合作夥伴發佈您提供轉接連結的數量。

必須符合許多的要求，才會正確地填入這個頁面：

* 如果使用手動自訂連結追蹤，必須觸發   *`s.tl()`*&#x200B;請求，而且中間參數設定為 *e*。

* 如果使用自動自訂連結追蹤，必須符合下列所有要求：
* 

   * [ s.trackExternalLinks](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_trackexlinks.html) 必須設定為 *true*。

   * 使用者按下的連結不應匹配 [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html) 變數裡的任何值。
   * 如果實作 [s.linkInternalFilters](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_linkinfilters.html)，外部連結至少必須匹配在這個變數中設定的一個值。

* 如果未符合上述任何要求，則點擊不會填入這個報告。

* 
* 和所有的自訂連結追蹤點擊一樣，會刪除影像請求裡的 [s.pageName](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_pagename.html)，以防止頁面檢視膨脹。
* 您可以使用趨勢和排名格式檢視這個報告。
* 此報告可使用搜尋篩選器尋找特定明細項目。
* 您可以透過「管理工具」以其他任何流量變數透過「管理工具」以其他任何變數建立[劃分](/help/analyze/reports-analytics/reports-customize/breakdowns.md)。
* [例項](/help/components/c-variables/c-metrics/metrics-instance.md)是這個報告中唯一提供的預設量度，會計算退出連結觸發的次數。
* 可以針對這份報告啟用每日、每週、每月和每季的訪客。但是，只有 Adobe 代表能夠啟用，而且必須另外收費。啟用任何自訂連結追蹤變數的獨特訪客可大幅減少報告套裝的延遲。

