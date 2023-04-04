---
title: 資料來源常見問題集
description: 有關資料來源的常見問題。
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 7%

---

# 資料來源常見問題集

有關資料來源的常見問題。

+++使用資料來源的成本為何？
資料來源不會產生任何費用，也不會計入伺服器呼叫使用量。 [完全處理資料來源](full-processing-eol.md) 會計入伺服器呼叫。
+++

+++資料來源對eVar的歸因和過期有何影響？
如果資料來源和線上點擊之間的transactionID相符，則相關的eVar值會假設相同的歸因和過期時間，就像線上上點擊上設定的一樣。

透過資料來源上傳的所有其他資料沒有任何歸因或過期。
+++

+++資料來源對頁面檢視、造訪或不重複訪客等預設量度有何影響？
透過資料來源上傳的資料不會影響 [頁面檢視](/help/components/metrics/page-views.md), [瀏覽](/help/components/metrics/visits.md)，或 [不重複訪客](/help/components/metrics/unique-visitors.md) 無論如何。 其影響的唯一預設量度包括 [發生次數](/help/components/metrics/occurrences.md).
+++

+++我可以刪除使用資料來源匯入的資料嗎？

**否。** 使用資料來源上傳至報表的資料為 **永久**. 匯入後即無法移除，甚至無法透過Adobe移除。 Adobe強烈建議先將資料來源資料上傳至測試報表套裝，然後再將其上傳至生產報表套裝。
+++

+++一次可匯入多少資料?

如果大小超過 50 MB 就會暫停處理，直到大小總計低於 50 MB 才會繼續。請確定FTP站台上所有檔案的總大小小於50 MB。
+++

+++如果透過資料來源將負值傳入報表，會發生什麼事？

值將因此減少。有些組織會使用負資料來源值來嘗試修正資料。 負面資料來源值可能會以您不樂見或非預期的方式影響報表。 Adobe建議僅使用負面資料來源作為最後手段。
+++

+++副檔名是否區分大小寫？
是。副檔名為 `.TXT` 或 `.FIN` 不會處理。 請確定副檔名全部為小寫。
+++

+++我可以新增多少欄至資料來源檔案？
如果資料源檔案全部都是有效的列，則可以在其中包含任意數量的列。 請參閱 [檔案格式](file-format.md) ，取得有效變數/欄名稱的清單。
+++

+++我可以不使用Adobe提供的FTP位置來使用資料來源嗎？
您可以使用 [資料來源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，可讓您直接將API呼叫傳送至Adobe。 這些API呼叫包含 `UploadData` 方法，可讓您透過JSON物件裝載傳送資料。
+++
