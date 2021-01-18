---
title: 完整審視
description: 每 6 個月審視一次實作，確保實作符合業務需求和 KPI。
translation-type: tm+mt
source-git-commit: ad7274dbed3b85ca24cd92bf3a0d36d1f2e3597b
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 100%

---


# 完整審視 (每年審視實作 2 次)

為何應每 6 個月審視實作一次？因為您必須確認實作符合業務需求！建議趁資料品質問題還不嚴重，尚未影響相關人員的信心前就及早處理。除了每 6 個月完整審視一次之外，每次網站發佈後，您也應該進行[重點審視](/help/implement/review/focused-review.md)。

## 1. 確認您的實作仍完全符合我們的業務需求。

與企業負責人及/或分析人員開會，檢討日新月異的業務需求。針對實作未能滿足的任何需求或測量機會，了解應如何更新 KPI 和測量計畫。別忘了在 [BRD 和 SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=zh-Hant#implementation) 中記錄變更項目。

## 2. 確認量度和變數仍正常運作。

按照對業務的重要程度，快速審視所有量度和變數，確認其能正確收集資料。從您最重要的度量和變數開始，也就是與 [5 大 KPI](https://experienceleague.adobe.com/docs/analytics/implementation/review/define-kpis.html?lang=zh-Hant#review) 相關的度量和變數。執行方法：

* 建立控制面板，檢視量度和變數的每月趨勢 (或為每個量度和變數設定[智慧型提醒](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace))，以確保獲得的資料符合預期，而且資料正確無誤。如果有任何不一致的地方，請檢查資料層、標籤管理程式規則和處理規則，從中尋找原因。
* 重新執行 [Analytics 運作狀態控制面板](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252)，監控量度和變數的主要趨勢。

避免實作牽涉太多不需要的量度和變數。停用業務不再需要或使用的量度或變數。建議您刪除這些項目或之後再重新利用。

## 3. 更新您的 KPI。

更新業務目標後，請重新評估您是否確實選擇 5 個&#x200B;*最重要*&#x200B;的關鍵績效指標 (KPI)。只能選 5 個！這些 KPI 可以是營收之類的量度或單次造訪收入等計算量度；量度中也可以使用變數。如需詳細資訊，請參閱[定義 5 大 KPI](/help/implement/review/define-kpis.md)。
