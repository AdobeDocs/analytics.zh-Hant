---
title: 疑難排解資料是否存在
description: 了解在報表中未看到資料時，可以採取哪些步驟。
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 1%

---


# 疑難排解資料是否存在

在Analysis Workspace中，有些專案設定會傳回零列。 在Reports &amp; Analytics中，檢視特定報表會傳回下列訊息：

**「沒有選定條件的資料。」**

使用下列步驟來判斷報表為何不顯示資料。

## 資料存在，但已過濾掉

您的報表套裝包含資料，但報表中使用的特定元件會篩選掉所有資料。

* **區段**:區段可輕鬆防止所有資料出現在報表中。檢查所有區段定義並移除所有區段，查看區段是否導致您的資料無法顯示。
* **量度**:確認已使用正確的量度。將量度變更為[發生次數](/help/components/metrics/occurrences.md)，以確定量度不是沒有資料之報表的貢獻者。
* **日期範圍**:過去或未來任何時間的日期範圍過長都不會傳回資料。貴組織的[資料保留原則](data-retention.md)決定保留資料的距離。
* **篩選器**:移除報表中的所有搜尋篩選器。

## 資料不存在

如果沒有區段，則量度為「發生次數」，日期範圍為當月，且沒有搜尋篩選器，請檢查下列項目：

* **驗證報表套裝**:請確定您位於包含資料的報表套裝中。許多組織都有新的、測試或開發報表套裝，但通常不包含太多資料。
* **延遲**:如果檢視最近的資料，資料可能會延遲。如需詳細資訊，請參閱[延遲](latency.md) 。
* **驗證資料收集**:導覽至報表套裝應該追蹤的Web屬性，然後開啟 [Adobe除錯程式](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html)。載入頁面時，請確定Analytics影像要求存在。 如果您看到影像要求，請確定其使用正確的報表套裝ID、包含有效的[currencyCode](/help/implement/vars/config-vars/currencycode.md)，以及影像要求與報表套裝之間的[時間戳記支援](/help/implement/vars/page-vars/timestamp.md)相符。
