---
description: 在第 14 版中，唯一訪客是指在指定的時段內第一次瀏覽某網站的訪客。例如，假設獨特訪客一星期內可能瀏覽某網站十次，但若時段單位為星期，則一個獨特訪客只會在該星期被計算一次。該星期結束後，該獨特訪客就可以在新的時段內再被計算一次。
seo-description: 在第 14 版中，唯一訪客是指在指定的時段內第一次瀏覽某網站的訪客。例如，假設獨特訪客一星期內可能瀏覽某網站十次，但若時段單位為星期，則一個獨特訪客只會在該星期被計算一次。該星期結束後，該獨特訪客就可以在新的時段內再被計算一次。
seo-title: 不重複訪客
solution: Analytics
title: 不重複訪客
topic: 量度
uuid: ae210698-99f9-485e-a640-c7520807adc7
translation-type: tm+mt
source-git-commit: ed22e0520bf1c7427ead039fb1d0391f2f1e567f

---


# 不重複訪客

在第 14 版中，唯一訪客是指在指定的時段內第一次瀏覽某網站的訪客。例如，假設獨特訪客一星期內可能瀏覽某網站十次，但若時段單位為星期，則一個獨特訪客只會在該星期被計算一次。該星期結束後，該獨特訪客就可以在新的時段內再被計算一次。

## 第 14 版與第 15 版之間的差異

Version 14 does not remove duplicate [!UICONTROL Visits] and [!UICONTROL Unique Visitors] metrics from classifications-based reports. 例如，假設有兩個影片片段共用相同的分類，有一名訪客檢視了兩個片段，而在分類式報告中產生了兩次[!UICONTROL 瀏覽]和兩個[!UICONTROL 獨特訪客]。

第 15 版會從分類式報告中移除重複的[!UICONTROL 瀏覽]和[!UICONTROL 唯一訪客]。這將更為精確地測量[!UICONTROL 瀏覽]和[!UICONTROL 訪客]數，但相較於升級前收集的資料，這常會導致分類式報告中的[!UICONTROL 瀏覽]和[!UICONTROL 獨特訪客]量度降低。

| 使用 | 說明 |
|---|---|
| 流量 | 訪客是指進入您的網站的人。不要求使用永久性 cookie。 |
| 轉換 | 訪客是指進入您的網站的人。當發生有關轉換的事件或動作時就會被計算為一次。 |
| Ad Hoc Analysis | 訪客是指進入您的網站的人。不要求使用永久性 cookie。 |

請參 [閱獨特訪客報表——第15版和臨機分析](../../../components/c-variables/dimensionslist/reports-unique-visitors-v15-dsc.md#concept_877141D6D1E743DA9FAB41C72A8121C7)。

>[!MORELIKETHIS]
>
>* [每日不重複訪客](/help/components/c-variables/c-metrics/metrics-daily-unique-visitors.md)

