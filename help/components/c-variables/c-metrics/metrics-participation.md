---
description: 參與率量度會將成功事件的全部評分指派給瀏覽期間傳遞之 eVar 的所有值。參與率量度可用於判斷哪些頁面、促銷活動或其他自訂變數值對網站成功的貢獻最大。參與率是基於瀏覽。發生事件時，點擊前 (與包含點擊) 之瀏覽中的所有 eVar 值會收到參與率評分 (無論其過期設定違和)。
solution: Analytics
title: 參與率
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 參與率

參與率量度會將成功事件的全部評分指派給瀏覽期間傳遞之 eVar 的所有值。參與率量度可用於判斷哪些頁面、促銷活動或其他自訂變數值對網站成功的貢獻最大。參與率是基於瀏覽。發生事件時，點擊前 (與包含點擊) 之瀏覽中的所有 eVar 值會收到參與率評分 (無論其過期設定違和)。

See [Visitor Participation - Ad Hoc Analysis](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) for more information about how Ad Hoc Analysis uses participation.

參與率量度可對每個轉換事件進行兩項設定:

* **已停用**: 每個轉換事件的預設狀態。對此事件將不會收集參與率資料。
* **已啟用**: 對此事件會收集參與率資料。

> [!NOTE] 您最多可為100個自訂事件啟用參與率。 除此之外，您還可在[計算量度](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html)產生器中建立參與率量度。

參與率量度一經啟用後，即自動可供所有轉換報告使用。但參與率量度也可在您的要求下，在特定流量報告中受到檢視。您可以選擇要求讓參與率量度可用於特定的自訂流量報告中。

## 收入參與率範例 {#section_DAB6C348201B454BB4ED01313AA777AF}

假設有下列序列:

1. 使用者導覽至您的網站並搜尋「鞋子」。
1. 使用者接著搜尋「網球鞋」。
1. 使用者按下連往產品頁面的連結、將該項目新增至購物車，然後花費 120 美元購買。

在「內部搜尋詞」報告中顯示「收入」時，根據所選取的分配方法，您會看到下列項目:

* **第一個**: 「鞋子」獲得 120 美元的評分。「網球鞋」獲得 0 美元。
* **最後一個**: 「網球鞋」獲得 120 美元的評分。「鞋子」獲得 0 美元。
* **線性**: 每個促銷活動各獲得 60 美元的評分。

   參與率類似於線性分配，但它是將完整評分給予所有值。如果使用「收入 (參與率)」量度，將不考慮分配方法。此範例中的「收入 (參與率)」會對兩個搜尋詞都報告 120 美元。

>[!MORELIKETHIS]
>
>* [量度計算](/help/components/c-variables/c-metrics/metrics-calculations.md)

