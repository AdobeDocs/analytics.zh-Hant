---
title: 資料來源常見問題集
description: 與資料來源相關的常見問題。
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 4%

---

# 資料來源常見問題集

與資料來源相關的常見問題。

+++使用資料來源的成本為何？
資料來源不會產生任何費用，也不會計入伺服器呼叫使用量。 [完整處理資料來源](full-processing-eol.md) 在伺服器呼叫淘汰前計入這些呼叫。
+++

+++資料來源如何影響eVar的歸因和到期日？
如果transactionID在資料來源和線上點選之間相符，則關聯的eVar值會假設相同的歸因和到期日，就像它們線上上點選上設定一樣。

所有其他透過資料來源上傳的資料則沒有任何型別的歸因或有效期。
+++

+++資料來源對預設量度（例如頁面檢視、造訪或不重複訪客）有何影響？
透過資料來源上傳的資料不會影響 [頁面檢視](/help/components/metrics/page-views.md)， [造訪](/help/components/metrics/visits.md)，或 [不重複訪客](/help/components/metrics/unique-visitors.md) 任何方式。 它們影響的唯一預設量度包括 [發生次數](/help/components/metrics/occurrences.md).
+++

+++可以刪除使用資料來源匯入的資料嗎？

**不適用。** 使用資料來源上傳至報表的資料為 **永久**. 匯入後即無法移除，甚至無法透過Adobe移除。 Adobe強烈建議先將資料來源上傳至測試報表套裝，再上傳至生產報表套裝。
+++

+++一次可匯入多少資料？

如果大小超過 50 MB 就會暫停處理，直到大小總計低於 50 MB 才會繼續。請確定FTP站台上所有檔案的總計大小小於50 MB。
+++

+++如果我透過資料來源將負值傳入報表，會發生什麼事？

值會因此減少。 有些組織會使用負數資料來源值來嘗試更正資料。 負的資料來源值可能會以您不樂見或意外的方式影響報表。 Adobe建議僅將負數資料來源作為最後手段。
+++

+++副檔名是否區分大小寫？
是。副檔名為 `.TXT` 或 `.FIN` 不會處理。 請確認副檔名全部為小寫。
+++

+++我可以新增多少欄到資料來源檔案？
您可以視需要在資料來源檔案中加入儘可能多的欄（如果全部都是有效欄）。 另請參閱 [檔案格式](file-format.md) 以取得有效的變數/欄名稱清單。
+++

+++我可以不使用Adobe提供的FTP位置而使用資料來源嗎？
您可以使用 [資料來源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，可讓您直接將API呼叫傳送至Adobe。 這些API呼叫包括 `UploadData` 方法，可讓您透過JSON物件裝載傳送資料。
+++
