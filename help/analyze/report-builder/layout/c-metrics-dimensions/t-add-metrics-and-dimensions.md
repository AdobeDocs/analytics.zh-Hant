---
description: 將度量和維度新增至請求的步驟。
title: 新增度量和維度
topic: Report builder
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 新增度量和維度

將度量和維度新增至請求的步驟。

1. [在上建立資料請求](/help/analyze/report-builder/data-requests/data-requests.md) , [!UICONTROL Request Wizard: Step 1]然後按一下 **[!UICONTROL Next]**。
1. On the [!UICONTROL Request Wizard: Step 2], double-click metrics, or drag them to the desired position.

   ![步驟資訊](assets/adding_metrics.png)

   When you add metrics, they are not removed from the [!UICONTROL Metrics] tab, because you can display metrics multiple times within a request. 例如，您可以顯示小計度量以指出每個值相加的結果。然而，可用度量的清單會在您每次新增或移除維度時改變。

   You can add only metrics to the [!UICONTROL Metrics] layout section. 量度會新增至 [!UICONTROL Column Label] 版面中 [!UICONTROL Metric Header]。 If you move a [!UICONTROL Metric Header] from [!UICONTROL Column Layout] to [!UICONTROL Row Layout], it is displayed there and is used as a metric as a breakdown.

   請注意，搜尋列會顯示在「度量」標籤上，位在「度量」清單正上方。

   ![](assets/search_bar_metric.png)

   請記住：

   * 當您輸入搜尋字詞時，清單會自動更新，只顯示其標籤符合搜尋字詞的度量。
   * 相符項目不區分大小寫，且相當於「包含」搜尋。
   * 不支援完整文字搜尋或其他特殊搜尋標幟 (開始於、終止於、AND、OR 等)。

      退出請求精靈時 (亦即按一下「完成」或「取消」)、返回請求精靈的步驟 1 時，或變更度量類別時，都會清除搜尋字詞。

      下列情形不會清除搜尋字詞：

   * 您拖放 (或連按兩下) 清單中的一個度量項目，將它新增至「樞紐配置/自訂配置」度量面板。
   * 您從「樞紐配置/自訂配置」度量面板移除度量項目。
   * 您按一下「維度」標籤，接著返回「度量」標籤。
   * 您叫用退出後會返回請求精靈的步驟 2 的其他子表單 (強制或非強制回應)。這些表單範例包括

      * 維度篩選表單
      * 日期範圍格式化表單
      * 格式選項表單
      * 附加於開頭-結尾文字表單
      * 輸入範圍位置表單

1. (選用項目) 若要依度量排序請求，只要按一下度量標籤即可。
1. 以新增度量的方法新增維度。

On the [!UICONTROL Dimensions] tab, the system displays dimensions that break down or are a classification of any base report you select on Step 1, and on the configuration of the report suite. 將維度拖放在配置格線時，系統會將配置格線從樹狀檢視中移除，然後重新計算剩餘可用的維度的清單。

The [!UICONTROL Date] dimension is added automatically. Available date dimensions change depending on the selected granularity from the [!UICONTROL Request Wizard: Step 1]. (有效值為：

    * Hour
    * Day
    * Week
    * Month
    * Year
    * Date range (若未指定粒度)

1. 設定[格式選項](/help/analyze/report-builder/layout/t-format-display-headers.md)和篩選器，修改量度和維度。
1. 按一下 **[!UICONTROL Finish]**.
In the following example, dimensions relate to the [!UICONTROL Page] metric. 在這裡，維 [!UICONTROL Referring Domain] 度會建立和之間的劃分 [!UICONTROL Page] 報表 [!UICONTROL Referring Domain]。 The [!UICONTROL Dimension] tab is updated with only dimensions that you can add to a breakdown report.

![](assets/page_pageview_02.png)
