---
keywords: Analysis Workspace
title: 同類群組分析是什麼?
topic: Reports and analytics
uuid: 39a83f3a-15d1-41d7-bcdd-50c22aed8f1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 同類群組分析是什麼?

*`cohort`* 是指一段指定時間內，共享相同特徵的一組人。例如當您想知道一個同類群組與某個品牌的互動關係時，就很適合使用同類群組分析。您可輕易看出趨勢中的變化，然後據以做出回應。(網路上有提供同類群組分析的解釋，例如 [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis)。)

建立同類群組報表後，您可以組織其元件 (特定的維度、量度和區段)，接著將同類群組報表與他人共用。請參閱[組織與共用](/help/analyze/analysis-workspace/curate-share/curate.md)。

同類群組分析的用途範例:

* 推行專為刺激所需動作的促銷活動。
* 在客戶生命週期的正確時間點轉移行銷預算。
* 識別何時終止試用或優惠，以最大化價值。
* 獲得定價、升級路徑等領域的 A/B 測試相關想法。
* 在指導分析報表中檢視同類群組分析報表。
* 識別何時終止試用或優惠，以最大化價值。
* 獲得定價、升級路徑等領域的 A/B 測試相關想法。

所有具有 Analysis Workspace 存取權限的 Analytics 客戶皆可使用同類群組分析。

[在 YouTube 觀看「同類群組分析」](https://www.youtube.com/watch?v=kqOIYrvV-co&index=45&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)(4:36)

>[!IMPORTANT]
>
>同類群組分析不支援計算量度。

## 同類群組分析功能

2019 年 1 月，Adobe 推出了大幅增強的新版「同類群組分析」。這個版本能讓您對正在建立的同類群組進行更精細的控制。下列為主要的增強功能:

### 保留率表格

保留率同類群組報表會回傳訪客人數: 每個資料儲存格顯示該同類群組中，在該時段內執行了動作的原始訪客數目和百分比。您可以包含最多 3 個量度和最多 10 個區段。

![](assets/retention-report.png)

### 流失率表格

流失率同類群組與保留率表格相反，會顯示在一段時間中，離開或從未符合同類群組回傳條件的訪客。您可以包含最多 3 個量度和最多 10 個區段。

![](assets/churn-report.png)

### 滾動式計算

可讓您根據上一欄計算保留率或流失率，而非根據包含欄。

![](assets/cohort-rolling-calculation.png)

### 延時表格

衡量包含事件發生前後的經過時間。此工具非常適合用來進行事前/事後分析。「包含」欄位於表格的中央，包含事件前後的時段會顯示於兩側。

![](assets/cohort-latency.png)

### 自訂維度同類群組

根據選取的維度建立同類群組，而非根據以時間為主的同類群組 (預設)。使用行銷管道、促銷活動、產品、頁面、地區等 Adobe Analytics 維度，說明保留率在不同維度值的變化。

![](assets/cohort-customizable-cohort-row.png)

如需如何設定和執行同類群組報表的說明，請前往[設定同類群組分析報表](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

