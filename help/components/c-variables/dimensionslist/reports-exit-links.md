---
title: 退出連結
description: 關於訪客最常用來點按以離開網站的連結報表。
translation-type: ht
source-git-commit: be4c3ec95b9e93dda7603c0bdb178c0a54d800a0

---


# 退出連結

顯示使用者最常用來點按以離開網站的連結。這些連結通常指向合作夥伴或附屬網站；但是，它們也可能是任何您設有外部連結的位置。您可以使用這個報告來檢視最熱門的附屬機構連結，或者協助驗證您的合作夥伴發佈您提供轉接連結的數量。

必須符合許多的要求，才會正確地填入這個頁面：
* 如果使用自訂連結追蹤，則 `tl()` 發出請求時必須將中間參數設為 `e`。
* 如果使用自動自訂連結追蹤，必須符合下列所有要求：
   * 必須啟用 [trackExternalLinks](/help/implement/vars/config-vars/trackexternallinks.md) 變數。
   * 使用者點按的連結不應符合 [linkInternalFilters](/help/implement/vars/config-vars/linkinternalfilters.md) 變數裡的任何值。
   * 如果 [linkExternalFilters](/help/implement/vars/config-vars/linkexternalfilters.md) 變數存在，外部連結至少必須符合在這個變數中設定的一個值。
* 如果未符合上述任何要求，則點擊不會填入這個報表。
* 與所有自訂連結追蹤點擊一樣，[pageName](/help/implement/vars/page-vars/pagename.md) 變數會從影像請求中移除，以避免頁面檢視量度膨脹。
* 您可以使用趨勢和排名格式檢視這個報告。
* 此報告可使用搜尋篩選器尋找特定明細項目。
* 您可以透過「管理工具」以其他任何流量變數使用任何其他變數進行[劃分](/help/analyze/reports-analytics/reports-customize/breakdowns.md)。
