---
description: 使用關鍵量度摘要視覺效果，比較兩個時間軸的量度成效。
title: 關鍵量度摘要
feature: Visualizations
role: User, Admin
exl-id: c74e77ff-15d6-48f1-a845-85bdf3444c3a
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 96%

---

# 關鍵量度摘要 {#key-metric-summary}

>[!CONTEXTUALHELP]
>id="workspace_keymetricsummary_button"
>title="關鍵量度摘要"
>abstract="建立折線圖、摘要變更和摘要數字圖表組合的視覺效果。使用此視覺效果來比較兩個時段之間重要量度的趨勢分析。"


>[!BEGINSHADEBOX]

_本文記錄_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** 中的關鍵量度摘要視覺效果。_<br/>_請參閱[關鍵量度摘要](https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/visualizations/key-metric)，以取得本文的_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** 版本。_

>[!ENDSHADEBOX]


![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 關鍵量度摘要]**&#x200B;視覺效果可讓您查看一項重要的量度在單一時間範圍內的趨勢分析。也能讓您比較兩個時間範圍內的量度成效。它提供多個視覺效果合併成單一視覺效果的優勢。

* **[!UICONTROL 折線圖]**&#x200B;視覺效果會顯示主要和比較日期範圍的趨勢分析

* **[!UICONTROL 摘要百分比變更]**&#x200B;會顯示主要和比較日期範圍之間的量度增減

* 量度目前的總值 ([!UICONTROL **摘要數字**])

## 使用案例

此視覺效果處理各種常見的使用案例，包括：

* 分析嘗試了解本月創造的商機跟去年同一時間範圍相比之下的表現。

* 行銷人員探索特定本月與上個月之間銷售機會的銷售機會開發變化。

* 高階主管想要了解本季與上一季之間的新預約變化。

## 使用

1. 新增 ![KeyMetrics](/help/assets/icons/KeyMetrics.svg) **[!UICONTROL 關鍵量度摘要]**&#x200B;視覺效果。請參閱[新增視覺效果至面板](freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 透過選取「**[!UICONTROL 量度]**」、「**[!UICONTROL 主要日期範圍]**」、「**[!UICONTROL 比較日期範圍]**」(可選)，以及「**[!UICONTROL 篩選條件]**」(可選) 來設定視覺效果：

   ![關鍵量度設定顯示量度、主要日期範圍、比較日期範圍以及區段的選項。](assets/key-metrics-config.png)

   | 選項 | 說明 |
   | --- | --- |
   | **[!UICONTROL 量度]** | 選取想要檢查的量度。支援所有量度。 |
   | **[!UICONTROL 主要日期範圍]** | 任意形狀表格目前的日期範圍。<p>從資料視圖中的任何適用的日期範圍中進行選擇。</p> <p>如果您想要使用與視覺效果所在面板上相同的日期範圍，請選擇「[!UICONTROL **面板日期範圍**]」。</p> |
   | **[!UICONTROL 比較日期範圍]** | 您要與主要日期範圍進行比較的日期範圍。 |
   | **[!UICONTROL 區段 (選擇性)]** | 您對於此摘要感興趣的任何區段。 |

   {style="table-layout:auto"}

   >[!NOTE]
   >
   >當&#x200B;[!UICONTROL **主要日期範圍**]&#x200B;欄位設定為「[!UICONTROL **面板日期範圍**]」，**[!UICONTROL 比較日期範圍]**&#x200B;可自動更新，取決於您選擇的&#x200B;**[!UICONTROL 比較日期範圍]**&#x200B;選項是相對於主要日期範圍或固定。
   >
   >* **相對：** 如果將&#x200B;**[!UICONTROL 比較日期範圍]**&#x200B;欄位設定為相對於主要日期範圍的選項 (例如&#x200B;[!UICONTROL **前一天**]、[!UICONTROL **上一週的同日**]、[!UICONTROL **四週前的同一日**]&#x200B;等等)，則任何更新至&#x200B;[!UICONTROL **主要日期範圍**]&#x200B;欄位會導致 **[!UICONTROL 比較日期範圍]**&#x200B;自動更新至緊接面板日期範圍之後的時段。
   >* **固定：** 如果將&#x200B;[!UICONTROL **比較日期範圍**]&#x200B;欄位設定為固定日期範圍 (例如&#x200B;**2023 年 2 月 3 日**)，則對&#x200B;[!UICONTROL **主要日期範圍**]&#x200B;欄位或面板日期範圍進行的變更，不會影響&#x200B;[!UICONTROL **比較日期範圍**]。但是，對面板日期範圍的任何更新都會導致&#x200B;[!UICONTROL **主要日期範圍**]&#x200B;自動更新。

1. 選取「**[!UICONTROL 建置]**」。

關鍵量度摘要的輸出如下所示：

![顯示此量度、摘要變更、摘要數字及折線圖的關鍵量度輸出。](assets/key-metrics.png)

檢視此輸出時請考慮以下事項：

* **[!UICONTROL 前一期]**&#x200B;折線圖 (總是以灰色顯示) 對應至設定步驟中的&#x200B;**[!UICONTROL 比較日期範圍]**。

* 如果未在設定期間指定比較日期範圍，或在視覺效果設定中隱藏日期比較範圍，僅會顯示主要日期範圍的線圖。已隱藏此摘要變更。

* 您可以從此處將指標停留在線圖上，以查看個別天數的統計資料：


## 設定

建置視覺效果後，您仍可編輯原始設定。

1. 請選取視覺效果頂端的「![編輯](/help/assets/icons/Edit.svg)**[!UICONTROL 設定視覺效果]**」。

   您會返回原始設定對話框。

1. 依偏好變更設定。請選取「**[!UICONTROL 重設]**」以重設目前設定。請選取「**[!UICONTROL 建置]**」以重建視覺效果。

## 設定

作為視覺效果設定的一部分，特定的關鍵量度摘要設定可供使用。

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 強調百分比變化]** | 在視覺效果中心，以顯著粗體顯示摘要變更 |
| **[!UICONTROL 強調數字值]** | 在視覺效果中心，以顯著粗體顯示摘要數字 |
| **[!UICONTROL 可見圖例]** | 顯示或隱藏視覺效果底部的圖例 |
| **[!UICONTROL 顯示註解]** | 顯示或隱藏管理員新增的註解 |
| **[!UICONTROL 隱藏標題]** | 隱藏視覺效果的標題。 |
| **[!UICONTROL 百分比]** | 以百分比而非數字來顯示視覺效果。 |
| **[!UICONTROL 顯示趨勢線]** | 在視覺效果中顯示趨勢線。 |
| **[!UICONTROL 在趨勢線上顯示最大值和最小值]** | 在主要和比較折線圖上顯示或隱藏最小值和最大值 |
| **[!UICONTROL 顯示比較百分比和趨勢線]** | 顯示或隱藏比較資料。隱藏時，比較折線圖和摘要變更物件將會從視圖中隱藏。 |
| **[!UICONTROL 顯示總數]** | 顯示或隱藏摘要數字 |
| **[!UICONTROL 顯示原始差異]** | 顯示主要日期範圍與次要日期範圍中量度總值之間的原始差異 |
| **[!UICONTROL 縮簡值]** | 請選取「**[!UICONTROL 縮簡值]**」以智慧的方式縮簡數值。選取後，請輸入一個數字來定義縮簡的總數。例如：<br/><table><tr><td>**原始值**</td><td>**縮簡**</td><td>**結果**</td></tr><tr><td>$12,011,141.25</td><td>未選取</td><td align="right">$12,011,141.25</td></tr><tr><td>$12,011,141.25</td><td>已選取，設定為 1</td><td align="right">$12,000,000</td></tr><tr><td>$12,011,141.25</td><td>已選取，設定為 2</td><td align="right">$12,000,000</td></tr><tr><td>$12,011,141.25</td><td>已選取，設定為 2</td><td align="right">$12,011,000</td></tr><tr><td>$12,011,141.25</td><td>請選取，設定為 3</td><td align="right">$12,011,000</td></tr></table> |

## 編輯視覺效果

建立視覺效果後，您可以編輯原始設定。

1. 選取視覺效果右上角的![編輯](/help/assets/icons/Edit.svg)。


   您現在已返回原始[組態檢視](#configure)。

1. 依偏好變更量度、主要日期範圍、比較日期範圍或區段。

>[!MORELIKETHIS]
>
>[將視覺化新增至面板](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[視覺效果設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[視覺化內容選單](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)

