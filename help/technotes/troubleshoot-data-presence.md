---
title: 資料存在性疑難排解
description: 了解當您未在報表中看到資料時可以採取哪些步驟。
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '332'
ht-degree: 100%

---


# 資料存在性疑難排解

在 Analysis Workspace 中，某些專案設定會傳回零列。 在 Reports &amp; Analytics 中，檢視某些報表會傳回以下訊息：

**「所選的條件沒有任何資料。」**

使用下列步驟來判斷為何報表未顯示資料。

## 有資料存在，但是已被篩選掉

您的報表套裝包含資料，但報表中所用的特定元件會篩選掉所有資料。

* **區段**：區段可輕鬆地防止所有資料出現在報表中。 請檢查所有區段定義並移除所有區段，以了解區段是否導致您的資料無法顯示。
* **量度**：檢查以確定是否有使用正確量度。 將量度變更為「[發生次數](/help/components/metrics/occurrences.md)」可確保該量度不是導致報表沒有資料的原因。
* **日期範圍**：已過去很久的日期範圍或是將來的任何時間都不會傳回資料。 貴組織的[資料保留原則](data-retention.md)會決定要保留多久以前的資料。
* **篩選條件**：從報表中移除所有搜尋篩選條件。

## 資料不存在

如果沒有任何區段、量度為「發生次數」、日期範圍為當月，而且沒有搜尋篩選條件，請檢查以下事項：

* **驗證報表套裝**：確定您使用的報表套裝有包含資料。 許多組織有新的、測試中或開發中的報表套裝，這些報表套裝通常沒有太多資料。
* **延遲**：如果檢視最近的資料，資料可能只是延遲而已。 如需詳細資訊，請參閱「[延遲](latency.md)」。
* **驗證資料收集**：導覽至您的報表套裝應該追蹤的 Web 屬性，並開啟 [Adobe Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=zh-Hant)。 確定當您載入頁面時，有 Analytics 影像要求存在。 如果您看到影像要求，請確定它有使用正確的報表套裝 ID、包含有效的 [currencyCode](/help/implement/vars/config-vars/currencycode.md)，且影像要求與報表套裝之間的[時間戳記支援](/help/implement/vars/page-vars/timestamp.md)是相符的。
