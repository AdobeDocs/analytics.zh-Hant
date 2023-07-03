---
title: 衍生受事件影響的資料
description: 使用計算量度來修正受事件影響的趨勢資料。
exl-id: 0fe70c8b-fa07-47e4-b6b3-b55eebad1fef
feature: Event, Calculated Metrics
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 3%

---

# 衍生受事件影響的資料

如果您有資料 [受事件影響](overview.md)，您可使用計算量度來匯出事件持續時間的預估值。 例如，如果您有造成資料下降25%的事件，您可以將其用作計算量度中的乘數。

從細分和日期比較的角度，瞭解事件影響時，這些步驟的效果最佳。 請務必遵循 [將受事件影響的日期與先前的範圍比較](compare-dates.md) 和 [在分析中排除特定日期](segments.md) 在此頁面之前。

>[!NOTE]
>
>此方法是根據一組特定輸入和日期範圍進行估計。 這不是適用於所有使用案例或資料片段的完整解決方案。 此外，此方法要求受影響的日期範圍至少有1個點選可計算。

若要建立受影響時段的預估計算量度：

1. 為「受影響的天數」和「排除受影響的天數」建立兩個區段，如下所述 [在分析中排除特定日期](segments.md).
2. 導覽至 **[!UICONTROL 元件]** > **[!UICONTROL 計算量度]**.
3. 按一下「**[!UICONTROL 新增]**」。
4. 將以上兩個區段拖曳至定義畫布。 將兩者之間的運運算元變更為 `+` 加以總和。
5. 在兩個區段內新增所需的量度。 例如，您可以使用「造訪」量度。

   ![區段產生器](assets/event_segment_builder.png)

6. 按一下 **[!UICONTROL 新增]** 在「受影響的天數」容器的右上角，然後按一下 **[!UICONTROL 靜態數字]**. 將靜態數字設定為您要位移資料的百分比，如下所述 [將受事件影響的日期與先前的範圍比較](compare-dates.md). 在此範例中，位移為25%或1.25。

   ![靜態數字](assets/event_static_number.png)

7. 在趨勢自由表格中並排套用「修正」量度。 事件以外的所有天數皆反映其標準量度計數，而所有受影響天數則使用乘數位移。

   ![已更正的量度](assets/event_corrected.png)

8. 線上條視覺效果中檢視資料，以檢視修正後量度的效果。

   ![已更正的行](assets/event_line.png)
