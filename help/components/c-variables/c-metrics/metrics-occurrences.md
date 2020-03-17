---
description: 擷取特定值的次數，加上有指定值存留的頁面檢視數目。換句話說，發生次數是頁面檢視與頁面事件的總和。發生次數可在 Analysis Workspace 和「Ad Hoc Analysis」中使用。
title: 發生次數
topic: Metrics
uuid: ff999fba-fcb7-4b16-9446-001facd0f15d
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 發生次數

擷取特定值的次數，加上有指定值存留的頁面檢視數目。換句話說，發生次數是頁面檢視與頁面事件的總和。發生次數可在 Analysis Workspace 和「Ad Hoc Analysis」中使用。

## 比較例項與發生次數{#section_4B0741AC1A78456E98AE0D4D28D70D29}

下列是看起來相似的兩種量度：

**[例項](/help/components/c-variables/c-metrics/metrics-instance.md)**：設定變數之值的次數。

**發生次數**：某個值有設定或持續存在的總次數。

| 情況 | 說明 |
|---|---|
| 發生次數高於例項數 | 此情況通常出現在轉換變數上，因為此時發生次數也會包含變數的定義次數 (例項數)。 |
| 例項數高於發生次數 | 報告中不可能發生此情況，因為所有例項也會記錄為發生次數。 |
| 例項數等於發生次數 | 此情況最常出現在流量變數上，因為這些變數依其特性不會存留到下一個影像要求。 |

>[!MORELIKETHIS]
>
>* [例項](/help/components/c-variables/c-metrics/metrics-instance.md)

