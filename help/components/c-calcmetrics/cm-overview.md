---
description: 計算量度和進階計算量度是自訂量度，您可以從現有量度建立。
keywords: 計算量度；進階計算量度
title: 計算量度和進階計算量度
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 53%

---

# 計算量度和進階計算量度

計算量度和進階計算量度是自訂量度，您可以從現有量度建立。

我們的計算量度工具可讓您以極為靈活的方式建立、管理和規劃量度。無論您是行銷人員、產品經理或分析人員，不需變更 [!DNL Analytics] 實施作業就能詢問資料相關問題。每個 [!DNL Analytics] 套裝中可用的自訂量度為：

* Adobe [!DNL Analytics] Foundation：計算
* [Adobe Analytics Select](https://www.adobe.com/tw/data-analytics-cloud/analytics/select.html)：計算 + 進階計算
* [Adobe Analytics Prime](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/prime.html)：計算 + 進階計算
* [Adobe Analytics Ultimate](https://www.adobe.com/tw/data-analytics-cloud/analytics.htmlanalytics/ultimate.html)：計算 + 進階計算

以下是計算量度與進階計算量度功能的比較：

| 產生器選項 | 計算量度 | 進階計算量度 |
|---|---|---|
| [格式類型 (小數、時間、百分比、貨幣)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | 是 | 是 |
| [歸因變更 (預設、線性、參與率等)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| [量度類型 (標準、總計)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | 是 | 是 |
| 基本運算元 (加、減、乘、除) | 是 | 是 |
| [套用區段](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | 無 | 是 |
| [基本函數 (計數、abs 值、平均值等)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | 無 | 是 |
| [進階函數 (迴歸、if/then、t 分數等)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | 無 | 是 |

## 功能 {#section_A0A5C275B68A4D628950BBB0B1EE631F}

您可以

* 建立跨[!UICONTROL Analysis Workspace]、[!UICONTROL Report Builder]、[!UICONTROL 異常偵測]和[!UICONTROL 貢獻分析]的量度。
* 無需變更實作，即可建立衍生自報表執行時間的區段量度。 因為這些量度的根據是區段，所以可查看其歷史資料。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [計算量度](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

* 在報表套裝間共用量度。這表示所有新建立的量度都會套用至相同登入公司的所有報表套裝。
* （僅限進階計算量度）量度上的區段。 例如，您可以建立「新訪客」的量度，計算第一次進行工作階段的人員數量。

* （僅限進階計算量度）納入統計函式以協助您更清楚地描述資料。 例如，您可以計算報表中的項目數或加入每個項目的標準差數字。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [區段中的分段計算量度](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


## 限制 {#section_CB878B02451541D68A68B508D4DBD19A}

部分 [!DNL Analytics] 功能可讓您使用事件，但無法使用計算量度：

* Analysis Workspace 中的「副產品」
* [!UICONTROL Analysis Workspace 中的「同類群組分析」]
* [!UICONTROL Data Warehouse]
* [!UICONTROL 區段]
* [!DNL Analytics] for [!DNL Target]

## 工具 {#section_D65E9C067E9C45E1A50DD30F50561BB2}

以下是[!UICONTROL 計算量度]工具的簡短概觀：

| 工具 | 功能 |
|--- |--- |
| 計算量度產生器 | <ul><li>使用進階配置模型建立計算量度和進階計算量度。</li><li>將內嵌區段新增至量度公式</li><li>比較同一份報表中的區段。例如，比較當地訪客和國際訪客。</li><li>使用統計函式</li><li>提供詳細的量度說明（顯示其用途、使用位置和不使用位置）</li><li>將定義複製到新量度中</li><li>提供內嵌量度預覽</li><li>設定量度極性，以指出當特定自訂事件（量度）上升時是有利還是不利</li><li>標籤量度</li></ul> |
| 計算量度管理員 | <ul><li>與其他人共用量度&lt;/li<li>核准和管理量度</li><li>組織（標籤）量度，方便使用者尋找</li><li>刪除量度</li><li>重新命名量度</li></ul> |
| 量度選擇器邊欄 | 可讓您搜尋量度，並將其新增/套用至報表。 您也可以變更排序順序（選項為：字母順序、建議、經常使用、最近使用。） 此外，您可以篩選報表套裝，以僅顯示特定報表套裝中建立的量度。  若要存取此「量度選擇器」，請按一下報表左側的「量度」圖示。 |
| 計算量度的 API | Adobe Analytics 2.0 API 集的一部分。 |
