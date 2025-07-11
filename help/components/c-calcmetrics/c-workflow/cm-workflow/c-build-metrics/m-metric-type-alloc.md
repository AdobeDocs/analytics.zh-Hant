---
description: 了解關於量度類型和歸因。
title: 量度類型和歸因
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: ht
source-wordcount: '607'
ht-degree: 100%

---

# 量度類型和歸因 {#metric-type-attribution}

您可以在計算量度定義中為量度設定量度類型和[歸因模型](#attribution-models)。

1. 在量度元件中選取「![設定](/help/assets/icons/Setting.svg)」。
1. 在快顯對話框中：

   ![量度類型和歸因](assets/cm-type-alloc.png)

   * 指定&#x200B;**[!UICONTROL 量度類型]**：

     | 量度類型 | 定義 |
     |---|---|
     | **[!UICONTROL 標準]** | 如果某個公式由單一標準量度組成，則其顯示的資料將與其非計算量度相對應公式一樣。標準量度適合用來建立每個行項目專屬的計算量度。 <p>例如，![事件](/help/assets/icons/Event.svg)**[!UICONTROL 「訂單數」]**![除](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg)**[!UICONTROL 「造訪數」]**&#x200B;會採用該特定條列項目的訂單數，然後除以該特定條列項目的造訪數。 |
     | **[!UICONTROL 總計]** | 使用適用於每個條列項目報告期間的&#x200B;**[!UICONTROL 總計]**。如果公式是由單一總計量度組成，則會在每個條列項目顯示相同總計。當您要建立與資料總計比較的計算量度時，適合使用總計量度。 <p>例如，![事件](/help/assets/icons/Event.svg)**[!UICONTROL 「訂單數」]**![除](/help/assets/icons/Divide.svg) ![事件](/help/assets/icons/Event.svg)**[!UICONTROL 「總造訪數」]**&#x200B;會顯示相較於所有造訪數的訂單比例，而不只是特定條列項目的造訪數。在此範例中，您在計算量度中指定 ![事件](/help/assets/icons/Event.svg)**[!UICONTROL 「造訪數」]**&#x200B;量度的&#x200B;**[!UICONTROL 「總量」]**，會自動將其轉換為 ![事件](/help/assets/icons/Event.svg)**[!UICONTROL 「總造訪數」]**。 |

   * 指定&#x200B;**[!UICONTROL 歸因]**。

      1. 您可以執行下列兩個動作中的一個:

         * 停用「**[!UICONTROL 使用非預設歸因模式]**」，以便使用預設欄歸因模型，也就是「上次接觸時間」且回顧期為 30 天。
         * 啟用「**[!UICONTROL 使用非預設歸因模型]**」。在「**[!UICONTROL 欄歸因模型]**」對話框。

            * 從[歸因模型](#attribution-models)中選取&#x200B;**[!UICONTROL 「模型」]**。
            * 從[容器](#container)選項中選取&#x200B;**[!UICONTROL 「容器」]**。
            * 從[回顧期間](#lookback-window)選項中選取&#x200B;**[!UICONTROL 「回顧期間」]**。如果選取&#x200B;**[!UICONTROL 「自訂時間」]**，您可以使用&#x200B;**[!UICONTROL 「分鐘」]** (最多以&#x200B;**[!UICONTROL 「季」]**) 來定義時段。

      1. 請選取「**[!UICONTROL 套用]**」，以套用非預設歸因模型。選取「取消」，即可取消。

     如果您已定義非預設歸因模型，請選取「**[!UICONTROL 編輯]**」來修改選擇內容。

請參閱[範例](#example)，了解使用歸因模型、容器及回顧期間的範例。


## 歸因模型 {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="使用非預設歸因模式"
>abstract="為所選的量度啟用非預設歸因模型。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="模型"
>abstract="選取此量度的歸因模型。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="上次接觸"
>abstract="100% 功勞歸於訪客看到的最後一個維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="首次接觸"
>abstract="100% 功勞會歸於訪客看到的第一個維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="線性"
>abstract="功勞平均分佈在所有維度值上。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="參與率"
>abstract="100% 功勞歸於訪客看到的每個維度值。<br/>欄總計會出現浮報現象。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="同一次接觸"
>abstract="功勞僅給予與轉換同一事件中發生的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="同一次接觸"
>abstract="功勞僅給予與轉換同一事件中發生的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U 型"
>abstract="40% 功勞歸於第一個維度值，40% 歸於最後一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J 曲線"
>abstract="60% 功勞歸於最後一個維度值，20% 歸於第一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J 曲線"
>abstract="60% 功勞歸於最後一個維度值，20% 歸於第一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="反向 J"
>abstract="60% 功勞歸於第一個維度值，20% 歸於最後一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="反向 J"
>abstract="60% 功勞歸於第一個維度值，20% 歸於最後一個維度值，20% 則分配到中間的維度值。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="時間耗損"
>abstract="在時間上最接近轉換的維度值獲得最多功勞。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="自訂"
>abstract="根據歸因加權定義您自己的位置。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="自訂"
>abstract="根據歸因加權定義您自己的位置。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="演算法"
>abstract="功勞是根據統計演算法動態決定的。"

{{attribution-models-details}}


## 容器 {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="容器"
>abstract="選取容器以設定所需的歸因範圍。"

{{attribution-container}}


## 回顧視窗 {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="回顧視窗"
>abstract="此設定可決定要為每個轉換套用的資料歸因期間。"

{{attribution-lookback-window}}

## 範例

{{attribution-example}}


<!--
When [building a calculated metric](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), you can specify the metric type and the attribution model.

## Metric type

To specify the metric type when building a calculated metric:

1. Select the gear icon next to the metric whose type you want to select.

   ![](assets/cm-type-alloc.png) 

1. Choose from the following options:

   |  Metric Type  | Definition  |
   |---|---|
   |  Standard  | These metrics are the same metrics used in standard [!DNL Analytics] reporting. If a formula consisted of a single standard metric, it displays identical data to its non-calculated-metric counterpart. Standard metrics are useful for creating calculated metrics specific to each individual line item. For example, [Orders] / [Visits] takes orders for that specific line item and divides it by the number of visits for that specific line item.  |
   |  Grand total  | Use Grand total for the reporting period in every line item. If a formula consisted of a single Grand total metric, it displays the same total number on every line item. Grand total metrics are useful for creating calculated metrics that compare against site total data. For example, [Orders] / [Total Visits] shows the proportion of orders against ALL visits to your site, not just the visits to the specific line item.  |

## How linear allocation works

[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) is how allocation models in calculated metrics are evaluated.

For a full list of non-default attribution models and lookback windows supported, see [Attribution models and lookback windows](/help/analyze/analysis-workspace/attribution/models.md).

The following example illustrates how calculated metrics with linear allocations work in reporting: 

| | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
|Data Sent In|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|
|Last Touch eVar|PROMO A|PROMO A|PROMO A|PROMO B|PROMO B|PROMO C|$10|
|First Touch eVar|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|PROMO A|$10|
|Example prop|PROMO A|-|PROMO A|PROMO B|-|PROMO C|$10|

In this example, the values A, B, and C were sent into a variable on hits 1, 3, 4, and 6 before a $10 purchase was made on hit 7. In the second row, those values persist across hits on a last touch visit basis. The third row illustrates a first-touch visit persistence. Finally, the last row illustrates how data would be recorded for a prop which does not have persistence.

-->