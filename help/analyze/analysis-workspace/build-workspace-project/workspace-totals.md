---
description: Workspace 總計的計算方式。
title: Workspace 總計
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Workspace 總計

在自由表格中，每個劃分層級都會顯示總列數，當中會顯示兩個總計數字：

* **[!UICONTROL Grand Total]** （灰色的「out」數字）-此總計代表所有已收集的點擊，有時稱為「報表套裝總計」。 在面板層級或自由表格內套用區段時，這項總計會經過調整，藉此反映所有符合區段條件的點擊。
* **[!UICONTROL Table Total]** （黑色數字）-此總計通常等於或為的子集 [!UICONTROL Grand Total]It reflects any table filters applied within the freeform table, including the [!UICONTROL Include None] option.

![](assets/total-row.png)

## 顯示總計設定

在 **[!UICONTROL Column Settings]**&#x200B;下面，可以選擇 **[!UICONTROL Show Totals]** 和 **[!UICONTROL Show Grand Total]**。 如果取消勾選這些設定，總計就會從表格中遭到移除。在使用某些[計算量度的情況](https://docs.adobe.com/content/help/zh-Hant/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html)下，總計可能會不符常理，此時就需要用到這項操作。

![](assets/column-settings-total.png)

## 靜態列總計設定

[靜態列總計](https://docs.adobe.com/content/help/zh-Hant/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) ，其行為不同，並受控制 **[!UICONTROL Row Settings]**。

* **[!UICONTROL Show sum of current rows as the total]** -這會顯示表格中各列的用戶端總和，這表示總計不會 **去重複** （例如瀏覽或訪客）。
* **[!UICONTROL Show Grand Total]** -這會顯示伺服器端總和，這表示總計會去重複化度量，例如瀏覽或訪客。

![](assets/static-rows.png)

## 常見問題集

| 問題 | 回答 |
|---|---|
| 灰色欄的百分比以哪些「總計」為依據？ | 這取決於以下位 **[!UICONTROL Percentages]** 置的設定選擇 **[!UICONTROL Row Settings]**:<ul><li>依欄計算百分比 - 此為預設設定。百分比將以「表格總計」為依據。</li><li>依列計算百分比 - 百分比將以「總量」為依據。</li></ul> |
| 設定對總計 **[!UICONTROL Include Unspecified (None)]** 有何影響？ | If the **[!UICONTROL Include Unspecified (None)]** setting is unchecked, the None/Unspecified row will be removed from the table, the Table Total, and will carry through to any calculated metrics that use [&#39;Total&#39; metric types](https://docs.adobe.com/content/help/zh-Hant/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| 如果在自由表格套用自訂表格篩選器，篩選器是否會採計我的所有計算量度和條件式格式？ | 目前不會。**[!UICONTROL Include Unspecified (None)]** 將被納入，但自訂表格篩選器將不會影響下列項目：<ul><li>條件式格式使用的欄最大值/最小值範圍會檢查所有資料。</li><li>運用量度類型的計 **[!UICONTROL Grand Total]** 算量度。</li><li>內含的函數可計算自由表格中所有列的計算量度，例如「欄加總」、「欄最大值」、「欄最小值」、「計數」、「平均值」、「中位數」、「百分位數」、「四分位數」、「列計數」、「標準差」、「變數」、「累積」、「累積平均值」、「迴歸變數」、「T 分數」、「T 檢定」、「Z 分數」、「Z 檢定」。</li></ul> |
| In Calculated Metrics, what does the **[!UICONTROL Grand Total]** metric type reflect? | **[!UICONTROL Grand Total]** 繼續引用 **[!UICONTROL Grand Total]**，且不會反映套用至表格或的篩選 **[!UICONTROL Table Total]**。 |
| 如果資料經由自由表格複製貼上或透過 CSV 下載，系統會顯示哪項總計？ | 總行將僅反映列 **[!UICONTROL Table Total]** 設定，並遵守列 **[!UICONTROL Show Totals]** 設定。 |

