---
description: 色階分佈圖是 Analysis Workspace 中的新視覺效果類型。
title: 色階分佈圖
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 色階分佈圖

色階分佈圖類似於長條圖，但前者將數字分組為範圍 (貯體)。Analytics 會自動將數字分組至範圍貯體，但您可以在「[進階設定](#section_09D774C584864D4CA6B5672DC2927477)」中變更設定。

## 建立色階分佈圖 {#section_74647707CC984A1CB6D3097F43A30B45}

若要建立色階分佈圖：

1. Click **[!UICONTROL Visualizations]** in the left rail.
1. Drag **[!UICONTROL Histogram]** to the panel.
1. Choose a Metric to drag to the Histogram visualization and click **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE]色階分佈圖僅支援標準量度，不支援計算量度。

這裡我們使用了每個獨特訪客的頁面檢視次數量度。第一個 (最左邊) 貯體對應至每個獨特訪客 1 次頁面檢視、第二個貯體對應至 2 次頁面檢視，以此類推。

![](assets/histogram2.png)

## 進階設定 {#section_09D774C584864D4CA6B5672DC2927477}

若要調整色階分佈圖設定，請按一下右上角的「設定」(「齒輪」) 圖示。您可以修改的設定如下：

| 色階分佈圖設定 | 用途 |
|---|---|
| 起始貯體 | 決定色階分佈圖開始使用的貯體。「1」是預設值。您可設定從 0 開始的數字，一直到無限大 (無負數)。 |
| 量度貯體 | 可讓您增加/減少資料範圍 (貯體) 的數目。貯體的最大數量是 50。 |
| 量度貯體大小 | 可讓您設定每個貯體的大小。例如，您可將貯體大小從 1 次頁面檢視變更為 2 次頁面檢視。 |
| 計算方法 | 可讓您選擇[訪客](https://marketing.adobe.com/resources/help/zh_TW/reference/visitors.html)、[造訪](https://marketing.adobe.com/resources/help/zh_TW/reference/metrics_visit.html)或[點擊](https://marketing.adobe.com/resources/help/zh_TW/reference/hit.html)。例如，每次造訪的頁面檢視數、每個訪客的頁面檢視數，或每次點擊的頁面檢視數。若為點擊，自由表格會將「發生次數」設為 Y 軸的量度。 |

**範例**：

* 起始貯體：1、量度貯體：5、量度貯體大小：2 會產生這個色階分佈圖：1-2、3-4、5-6、7-8、9-10。
* 起始貯體：0、量度貯體：3、量度貯體大小：5 會產生這個色階分佈圖：0-4、5-9、10-14

## 檢視和編輯色階分佈圖資料 {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

To view or change the data source for the histogram chart, click the dot next to the Histogram header to go to **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

此表格中顯示的預先建立區段是內部區段，不會顯示在區段選取器中。Click the &quot;i&quot; icon next to the segment name, then click **[!UICONTROL Make public]** to make the segment public.

![](assets/prebuilt_segments.png)

若想探索管理自由資料表及其他視覺效果的其他方法，例如進行資料劃分，請前往[此處](https://marketing.adobe.com/resources/help/zh_TW/analytics/analysis-workspace/freeform-analysis-visualizations.html)。
