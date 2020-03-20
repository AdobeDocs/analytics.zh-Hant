---
title: 退出連結
description: 報告訪客離開您網站時最常點按的連結。
translation-type: tm+mt
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# 退出連結

顯示訪客離開網站時最常被點按的連結。 這些連結通常指向合作夥伴或附屬網站；但是，它們可以是您有外部連結的任何位置。 您可以使用這個報告來檢視最熱門的附屬機構連結，或者協助驗證您的合作夥伴發佈您提供轉接連結的數量。

必須符合許多的要求，才會正確地填入這個頁面：
* 如果使用手動自訂連結追蹤， `tl()` 則必須在中間參數設為時引發請求 `e`。
* 如果使用自動自訂連結追蹤，必須符合下列所有要求：
   * 必須 [啟用trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) 變數。
   * The link the user clicked on must not match any values within the [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) variable.
   * If the [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) variable exists, the external link must match at least one of the values set in this variable.
* 如果未符合上述任何要求，點擊不會填入此報表。
* 與所有自訂連結追蹤點擊一樣， [pageName](/help/implement/vars/page-vars/pagename.md) 變數會從影像請求中移除，以防止頁面檢視量度膨脹。
* 您可以使用趨勢和排名格式檢視這個報告。
* 此報告可使用搜尋篩選器尋找特定明細項目。
* 您可以透過「管理工具」以其他任何流量變數 使 [用任何](/help/analyze/reports-analytics/reports-customize/breakdowns.md) 其他變數進行劃分。
