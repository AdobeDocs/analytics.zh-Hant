---
description: 讓您輕鬆直觀地看到Analysis Workspace的比較資料，如與上個月、去年等的建築物比較。
title: 組合圖可視化
feature: Visualizations
role: User, Admin
source-git-commit: 4cc3a34eab5d29cb62244978c848d303d4754409
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 31%

---


# 組合圖表

>[!NOTE]
>
>此功能目前正在進行[有限測試](/help/release-notes/releases.md)。

的 [!UICONTROL 組合圖] 可視化使快速構建比較可視化變得容易，而無需先構建表。 您可以輕鬆地以行/欄組合查看資料趨勢。

使用 [!UICONTROL 組合圖] 至

* 將上週的訂單與上個月（和去年）的訂單進行比較 — 只需幾下點擊。

* 快速分析和比較多個度量(例如 [!UICONTROL 獨特訪問者] 和 [!UICONTROL 收入])的對齊。

* 根據函式分析度量(例如 [!UICONTROL 累計平均值])。

記住，你可以

* 在單個中添加多個比較 [!UICONTROL 組合圖]。
* 如果添加一個或多個比較，則它們必須是相同類型，例如 [!UICONTROL 時間比較]。
* 最多可加5個比較。
* 最多可將3個篩選器（段）應用到度量。

## 生成組合圖

1. 從左滑軌的「可視化」下拉清單中，拖動 [!UICONTROL 組合圖] 顯示為空白麵板。

   ![](assets/combo-chart-build.png)

1. 從下拉清單中，選擇X軸的尺寸和Y軸的度量。

1. 選擇的類型 [!UICONTROL 行比較] 你想用。

   | 行比較類型 | 定義 |
   | --- | --- |
   | **[!UICONTROL 時間比較]** | 最常見的比較類型 — 例如，將此時段與4週前進行比較。 如果已選擇 [!UICONTROL 時間比較]，對要比較的時段進行輔助選擇。<p>![](assets/combo-time-period.png) |
   | **[!UICONTROL 其他量度]** | 比如，你可以 [!UICONTROL 收入] 到另一個指標。<p>![](assets/combo-2metrics.png) |
   | **[!UICONTROL 函數]** | 你可以引入一個 [!UICONTROL 平均] 比較。 請參見下面支援的函式清單。<p>![](assets/combo-functions.png) |

   {style=&quot;table-layout:auto&quot;}

1. 按一下&#x200B;**[!UICONTROL 「建置」]**。

   輸出將類似於以下內容：

   ![](assets/combo-output.png)

   當前時段顯示在條形圖中，比較時段由折線圖表示。 折線圖上的圓點稱為「條形鐘」。

## 支援的函式

如果您選擇 **[!UICONTROL 函式]** 的 [!UICONTROL 行比較類型]，將返回您選擇的度量的函式。

| 函數 | 定義 |
| --- | --- |
| **[!UICONTROL 欄總和]** | 在列內（跨維的元素）添加度量的所有數值 |
| **[!UICONTROL 累積平均值]** | 傳回最後 N 列的平均值。 |
| **[!UICONTROL 中位數]** | 傳回一欄中量度的中位數。中位數是位於一組數字中間的數字，也就是一半數字的值大於或等於中位數，另一半數字的值小於或等於中位數。 |
| **[!UICONTROL 累積]** | N行的累計和。 |
| **[!UICONTROL 欄最大值]** | 傳回量度欄中一組維度元素的最大值。 |
| **[!UICONTROL 平均值]** | 返回度量的算術平均值或平均值。 |
| **[!UICONTROL 欄最小值]** | 傳回量度欄中一組維度元素的最小值。 |

{style=&quot;table-layout:auto&quot;&quot;

下面是「收入」度量的累計平均值示例：

![](assets/combo-cumul-avg.png)

下面是具有累積平均和平均函式的組合圖示例：

![](assets/combo-two-functions.png)

## 組合圖設定

按一下組合圖右上角的齒輪表徵圖以更改其設定。

![](assets/combo-settings.png)

| 設定 | 定義 |
| --- | --- |
| **[!UICONTROL 可視化類型]** | 允許您切換到其他可視化類型。 |
| **[!UICONTROL 詳細程度]** | 若要取得最新式的視覺效果，您可在此下拉功能表中變更時間的詳細程度 (日、週、月等)。 |
| **[!UICONTROL 一般]** |  |
| **[!UICONTROL 百分比]** | 以百分比顯示值。 |
| **[!UICONTROL 可見圖例]** | 用於隱藏組合圖可視化的詳細圖例文本。 |
| **[!UICONTROL 限制最大項]** | 減少X軸上的項數。 如果您有大資料集，則只能顯示前10個項（或您選擇的任何值）。 |
| **[!UICONTROL 覆蓋]** | 線上上顯示或隱藏槓鈴。 |
| **[!UICONTROL 軸]** |  |
| **[!UICONTROL 顯示雙軸]** | 僅適用於具有兩個量度時 - 可在左側 (針對一個量度) 和右側 (針對另一個量度) 各顯示一個 Y 軸。當繪製的量度大小非常不同時，這項功能會很有用。雙軸顏色與表的顏色匹配，除非有多個比較。 在這種情況下，所有比較的顏色都是灰色。 |
| **[!UICONTROL 標準化]** | 強制量度為相同比例。當繪製的量度大小非常不同時，這項功能會很有用。 |
| **[!UICONTROL 顯示X軸]** | 顯示或隱藏x軸。 |
| **[!UICONTROL 顯示Y軸]** | 顯示Y軸或隱藏它。 |
| **[!UICONTROL 錨點Y軸為零]** | 如果圖表上繪製的點都遠高於零，則圖表預設會讓 Y 軸底部「不是零」。如果您勾選此方塊，Y 軸將強制固定於零 (並會重繪圖表)。 |

{style=&quot;table-layout:auto&quot;&quot;


