---
description: 使用線條圖視覺效果來描繪資料集的趨勢（以時間為基礎）。
title: 折線圖
uuid: 0508ff29-43fe-4f3a-a5f7-051869271b55
feature: Visualizations
role: User, Admin
exl-id: d177b39f-add7-4011-977a-1bdf3a9368cb
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 98%

---

# 折線圖 {#line}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_line_button"
>title="折線圖"
>abstract="建立折線圖視覺效果，顯示值在一段時間內如何變化。僅在使用時間當作維度時，才使用折線圖視覺效果。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文記錄_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 中的折線圖視覺效果。_<br/>_請參閱[折線圖](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/visualizations/line)，以取得本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** 版本。_

>[!ENDSHADEBOX]

![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL 折線圖]**&#x200B;視覺效果使用線條表示量度，以顯示一段期間的值的變化。僅在使用時間作為維度時，才使用折線圖視覺效果。

![折線圖視覺效果](assets/line-viz.png)


## 設定

作為[視覺效果設定](freeform-analysis-visualizations.md#settings)的一部分，可使用特定的折線圖視覺效果設定。

| 設定 | 說明 |
|---|---|
| **[!UICONTROL 詳細程度]** | 請從詳細程度下拉式清單中選取，以將趨勢視覺效果從每日變更為每週、每月等。詳細程度也會在資料來源表格中更新。 |
| **[!UICONTROL 顯示最小值]**<br/>**[!UICONTROL 顯示最大值&#x200B;]** | 您可以覆蓋最小值和最大值標籤以醒目提示顯示量度中的最小值和最大值。最小值/最大值是從視覺效果中的可見資料點衍生而來，而非維度中的完整數值集。<br/>![使用最小值和最大值標籤的覆蓋。](assets/min-max-labels.png) |
| **[!UICONTROL 顯示趨勢線]** | 您可以選擇新增迴歸或移動平均趨勢線至您的折線圖序列。趨勢線有助於描繪出資料中更清晰的模式。選取後，從清單中選取一個模型。請參閱[模型](#models)，以了解可用模型的概觀和說明。<br/>![線性趨勢線](assets/show-linear-trendline.png)。 |

>[!TIP]
>
>建議將趨勢線套用至不包括今天 (部分資料) 或未來日期的資料。今天或未來日期的資料會扭曲趨勢線。但是，如果您需要包含未來日期，請從資料中移除零，以防止這些日期出現偏差。請前往視覺效果的資料來源表格，選擇您的量度欄，然後啟用「**[!UICONTROL 欄位設定]** > **[!UICONTROL 將零解讀為無值]**」。



### 模型

所有回歸模型趨勢線都適合使用普通最小二乘法：

| 模型 | 說明 |
| --- | --- |
| **[!UICONTROL 線性]** | 為簡單的線性資料集建立最合適的直線，當資料以穩定速率增加或減少時非常實用。方程式：`y = a + b * x` |
| **[!UICONTROL 對數]** | 建立最合適的曲線，當資料變更率快速增加或減少，然後趨於平穩後相當實用。對數趨勢線可使用負值和正值。方程式：`y = a + b * log(x)` |
| **[!UICONTROL 指數]** | 建立曲線，當資料以不斷提高的速率上升或下降時相當實用。如果您的資料包含零或負值，則不應使用此選項。方程式：`y = a + e^(b * x)` |
| **[!UICONTROL 乘冪]** | 建立曲線，比較以特定速率增加的測量之資料集時相當實用。如果您的資料包含零或負值，則不應使用此選項。方程式：`y = a * x^b` |
| **[!UICONTROL 二次方]** | 找出拋物線形 (向上或向下凹入) 的資料集最合適的線條。方程式：`y = a + b * x + c * x^2` |
| **[!UICONTROL 移動平均]** | 根據一組平均值建立平滑趨勢線。移動平均也稱為滾動平均，會使用特定數量的資料點 (取決於[!UICONTROL 詳細程度]的選取項目)，並將平均值當做線條中的某個點。例如包括 7 天移動平均值或 4 週移動平均值。 |

>[!MORELIKETHIS]
>
>[將視覺化新增至面板](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[視覺效果設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[視覺化內容選單](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

