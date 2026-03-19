---
title: 單頁造訪次數 (量度)
description: 「頁面」維度項目在造訪中未變更的次數。
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 34%

---

# 單頁造訪次數

*此說明頁面說明「單頁造訪次數」作為量度時的運作方式。如需詳細資訊，請參閱[單頁造訪次數](../dimensions/single-page-visits.md)維度。*

**[!UICONTROL 單頁造訪次數]** [量度](overview.md)會顯示[頁面](../dimensions/page.md)維度專案在整個造訪中僅包含單一值的造訪次數。 當您想要了解短期造訪次數維度，但沒有設定像是[[!UICONTROL 跳出數]](bounces.md)那樣嚴格的規則時，此量度就會很有用。

## 此量度的計算方式

此量度的定義取決於[[!UICONTROL 計數重複執行個體]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings)的專案設定：

* **[!UICONTROL 計算啟用的重複執行個體]**：計算[!UICONTROL 頁面]維度包含單一造訪值的造訪次數。 如果訪客重新載入頁面，即不符合單頁造訪的資格。
* **[!UICONTROL 計算已停用的重複執行個體]**：計算[!UICONTROL 頁面]維度在整個造訪中包含單一唯一值的造訪次數。

不論&#39;[!UICONTROL Count repeat instances]&#39;專案設定為何，此量度都會遵循下列規則：

* 如果訪客引發連結追蹤呼叫，造訪仍符合單頁造訪的資格（[!UICONTROL 頁面]維度會從所有連結追蹤呼叫中移除）。
* 當[!UICONTROL 頁面]維度變更為第二個不重複值時，該次造訪即不再符合單頁造訪的資格。

如需量度之間的比較，請參閱[單次存取](single-access.md)。
