---
title: 資料來源常見問題集
description: 與資料來源相關的常見問題。
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 7%

---

# 資料來源常見問題集

與資料來源相關的常見問題。

+++使用資料來源的成本為何？
資料來源不會產生任何費用，也不會計入伺服器呼叫使用量。 [完整處理資料來源](full-processing-eol.md) 在停用前計入伺服器呼叫。
+++

+++資料來源如何影響eVar的歸因和到期日？
如果transactionID在資料來源和線上點選之間相符，則關聯的eVar值會假設相同的歸因和到期日，就像它們線上上點選上設定一樣。

透過資料來源上傳的所有其他資料並無任何型別的歸因或到期日。
+++

+++資料來源如何影響預設量度，例如頁面檢視、造訪或不重複訪客？
透過資料來源上傳的資料不會影響 [頁面檢視](/help/components/metrics/page-views.md)， [造訪](/help/components/metrics/visits.md)，或 [不重複訪客](/help/components/metrics/unique-visitors.md) 任何方式。 它們影響的唯一預設量度包括 [發生次數](/help/components/metrics/occurrences.md).
+++

+++我可以刪除使用資料來源匯入的資料嗎？

**否。** 使用資料來源上傳至報表的資料為 **永久**. 匯入後即無法移除，也無法透過Adobe移除。 Adobe強烈建議先將資料來源上傳至測試報表套裝，再上傳至生產報表套裝。
+++

+++一次可匯入多少資料?

如果大小超過 50 MB 就會暫停處理，直到大小總計低於 50 MB 才會繼續。請確定FTP站台上所有檔案的總大小小於50 MB。
+++

+++如果我透過資料來源將負值傳入報表，會發生什麼事？

值將因此減少。有些組織會使用負數資料來源值來嘗試更正資料。 負的資料來源值可能會以您不樂見或意外的方式影響報表。 Adobe建議僅在萬不得已時才使用負數資料來源。
+++

+++副檔名是否區分大小寫？
是。副檔名為的檔案 `.TXT` 或 `.FIN` 不會處理。 請確定副檔名全部為小寫。
+++

+++我可以新增多少欄至資料來源檔案？
您可以視需要為資料來源檔案加入任意數目的欄（如果全部為有效欄）。 另請參閱 [檔案格式](file-format.md) 以取得有效的變數/欄名稱清單。
+++

+++我可以不使用Adobe提供的FTP位置而使用資料來源嗎？
您可以使用 [資料來源API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/)，可讓您直接將API呼叫傳送至Adobe。 這些API呼叫包括 `UploadData` 方法，可讓您透過JSON物件裝載傳送資料。
+++
