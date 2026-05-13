---
title: 完整審視
description: 每 6 個月審視一次實施作業，確保實施作業符合業務需求和 KPI。
feature: Implementation Basics
exl-id: 235fc86e-e1b0-4b1a-a270-0dfba457a832
role: Admin, Leader
TQID: https://experienceleague.adobe.com/YQL-V84ZWAr8NqRp1snYZBgl7-3iIhhxWkWh6KTFKNM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 404
ht-degree: 73%

---

# 完整審視 (每年審視實施作業 2 次)

為何應每 6 個月審視實施作業一次？ 因為您必須確認實作符合業務需求！ 建議趁資料品質問題還不嚴重，尚未影響相關人員的信心前就及早處理。 除了每 6 個月完整審視一次之外，每次網站發佈後，您也應該進行[重點審視](/help/implement/review/focused-review.md)。

## &#x200B;1. 確認您的實作仍完全符合我們的業務需求

與企業負責人及/或分析人員開會，檢討日新月異的業務需求。 針對實施作業未能滿足的任何需求或測量機會，了解應如何更新 KPI 和測量計畫。 別忘了在 [BRD 和 SDR](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=zh-Hant#implementation) 中記錄變更項目。

## &#x200B;2. 確認量度和變數仍正常運作

按照對業務的重要程度，快速審視所有量度和變數，確認其能正確收集資料。 從您最重要的度量和變數開始，也就是與 [5 大 KPI](/help/implement/review/define-kpis.md#review) 相關的度量和變數。 執行方法：

* 建立控制面板，檢視量度和變數的每月趨勢（或為每個量度和變數設定[警報](/help/components/alerts/alerts-overview.md)），以確保獲得的資料符合預期，而且資料正確無誤。 如果有任何不一致的地方，請檢查資料層、標籤管理程式規則和處理規則，從中尋找原因。
* 重新執行 [Analytics 運作狀態控制面板](https://assets.adobe.com/public/8ff304bb-18e0-434b-54d1-39199422ba1c)，監控量度和變數的主要趨勢。

避免實作牽涉太多不需要的量度和變數。 停用業務不再需要或使用的量度或變數。 建議您刪除這些項目或之後再重新利用。

## &#x200B;3. 重新整理您的KPI

更新業務目標後，請重新評估您是否確實選擇 5 個&#x200B;*最重要*&#x200B;的關鍵績效指標 (KPI)。 只能選 5 個！ 這些 KPI 可以是營收之類的量度或單次造訪收入等計算量度；量度中也可以使用變數。 如需詳細資訊，請參閱[定義 5 大 KPI](/help/implement/review/define-kpis.md)。
