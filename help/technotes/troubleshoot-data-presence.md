---
title: 疑難排解資料存在問題
description: 瞭解在報表中未看到資料時，可採取哪些步驟。
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---


# 疑難排解資料存在問題

在分析工作區中，有些專案設定會傳回零列。 在「報告與分析」中，檢視特定報表會傳回下列訊息：

**&quot;沒有選定條件的資料。&quot;**

使用下列步驟來判斷報表不顯示資料的原因。

## 資料存在，但已篩選出

您的報表套裝包含資料，但報表中使用的特定元件會篩選掉所有資料。

* **區段**:區段可以輕鬆防止所有資料出現在報表中。 勾選所有區段定義並移除所有區段，以查看區段是否造成您的資料無法顯示。
* **量度**:檢查以確保使用正確的量度。 將量度變更為 [發生次數](/help/components/metrics/occurrences.md) ，以確定量度不是沒有資料的報表貢獻者。
* **日期範圍**:過去或未來的日期範圍過長不會傳回資料。 您組織的資料保 [留政策](data-retention.md) ，會決定保留資料的距離。
* **篩選**:從報表中移除所有搜尋篩選。

## 資料不存在

如果沒有區段，則量度為「發生次數」，日期範圍為目前月份，且沒有搜尋篩選器，請勾選下列項目：

* **驗證報表套裝**:請確定您位於包含資料的報表套裝中。 許多組織都有新的、測試或開發報表套裝，通常不包含太多資料。
* **延遲**:如果檢視最近的資料，資料可能會延遲。 如需詳 [細資訊](latency.md) ，請參閱延遲。
* **驗證資料收集**:導覽至您報表套裝應追蹤的Web屬性，並開啟 [Adobe除錯程式](https://docs.adobe.com/content/help/zh-Hant/debugger/using/experience-cloud-debugger.html)。 在載入頁面時，請確定Analytics影像要求存在。 如果您看到影像要求，請確定它使用正確的報表套裝ID、包含有效的 [currencyCode](/help/implement/vars/config-vars/currencycode.md)，以及該時間戳記支援 [](/help/implement/vars/page-vars/timestamp.md) ，以符合影像要求和報表套裝。
