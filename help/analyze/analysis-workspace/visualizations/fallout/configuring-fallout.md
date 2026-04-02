---
description: 瞭解如何設定並指定接觸點來建立多維度流失序列。
title: 設定流失視覺效果
feature: Visualizations
role: User, Admin
exl-id: 9d2a0163-a5cb-4a1c-97e9-e78a8f99aaee
source-git-commit: 121fac9958dc34be513a23d5c3ad76d5f0e6b665
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 30%

---

# 設定流失視覺效果

您可以指定&#x200B;**接觸點**&#x200B;來建立多維度流失序列。 在許多情況下，接觸點是您網站上的頁面。 不過，接觸點並不限於頁面。 例如，您可以新增事件 (例如件數)，以及不重複人員和回訪次數。您也可以新增維度，例如類別、瀏覽器型別或內部搜尋詞。

您甚至可以在接觸點內新增區段。 例如，您可能想要比較區段，例如iOS和Android使用者。 將所需區段拖曳至流失上方，這些區段的相關資訊會新增至流失報告中。如果只想顯示這些區段，您可以移除「所有造訪數」基線。

「流失」視覺效果對於可新增的接觸點數目或可使用的元件數目沒有限制。

您可以對維度、量度及區段進行路徑分析。例如，假設某人正在一個頁面上檢視`shoes, shirt`，而在下一個頁面上檢視`shirt, socks`。 來自鞋子的下一個產品流量報告會是上衣和襪子，「而非」上衣。

## 使用

1. 新增 ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL 流失]**&#x200B;視覺效果。請參閱[新增視覺效果至面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 將元件拖曳至&#x200B;**[!UICONTROL 新增接觸點]**&#x200B;下拉式功能表。

   >[!TIP]
   >
   >您可以將單一頁面新增至流失報表，而非整個維度。 按一下頁面維度上的向右箭頭![V形右](/help/assets/icons/ChevronRight.svg)，挑選特定頁面，例如&#x200B;**[!UICONTROL home]**，將其新增至流失報表。


   ![將首頁從首頁維度拖曳至新增接觸點欄位。](assets/fallout-drag.png)

1. 繼續新增接觸點，直到完成您的序列。

   長條灰色部分裡頭圈起來的數字，是接觸點之間的流失 (不是該點的整體流失)。長條圖綠色部分中的圓圈數字表示從上一個接觸點到目前接觸點的成功瀑布。

   ![流失視覺效果](assets/fallout-visualization.png)

   新增接觸點時，您可以進行下列任一項作業：

   * 將一個或多個其他元件拖曳到單一接觸點上，以組合多個元件。

     >[!NOTE]
     >
     >多個區段必須以 AND 連結，但多個項目 (例如維度項目和量度) 則須以 OR 連結。

   * 將接觸點拖曳至流失階層內的不同層級，以重新排序接觸點。

   * 將一個接觸點拖曳至另一個接觸點，以結合兩個接觸點。 當您看到單字&#x200B;**[!UICONTROL 合併]**&#x200B;時，請卸除接觸點。

   * 在路徑內將個別接觸點限製為下一次點選（而非&#x200B;*最終*）。 在每個接觸點下方，有一個選擇器，其選項為&#x200B;**[!UICONTROL 最終路徑]**&#x200B;和&#x200B;**[!UICONTROL 下一次點選]**，如下所示：

     | 選項 | 說明 |
     |---|---|
     | **[!UICONTROL 最終路徑]** (預設) | 計入的訪客最終&#x200B;*會*&#x200B;登陸路徑中的下一個頁面，但不一定是在下次造訪時。 |
     | **[!UICONTROL 下一個點選]** | 將登陸下一次點選路徑中下一頁的訪客計算在內。 |

   * 將滑鼠指標暫留在接觸點上，即可檢視流失和該層級的其他相關資訊。 資訊包括接觸點的名稱、人員計數和成功率。 您也可以比較其他接觸點的成功率。

## 設定

下列為可用的視覺效果設定：

| 流失容器 | 說明 |
|--- |--- |
| **[!UICONTROL 瀏覽]**&#x200B;或&#x200B;**[!UICONTROL 訪客]** | 在[!UICONTROL 次造訪]和[!UICONTROL 個訪客]之間切換，以分析人員路徑。 預設為[!UICONTROL 訪客]。 這些設定可協助您了解訪客層級的訪客參與程度 (跨越造訪)，或是將分析限制在單一造訪。 |


## 內容選單

作為視覺效果的一部分，可使用特定內容選單選項。

### 存取內容功能表

您可以透過下列其中一種方式來存取前後關聯功能表：

* 將滑鼠停留在視覺效果中的接觸點上，然後選取&#x200B;**[!UICONTROL 按一下以分析]**。

  ![從暫留存取內容功能表](assets/fallout-tooltip-analyze.png)

* 以滑鼠右鍵按一下視覺效果中的接觸點。

  ![流失選項](assets/fallout-options.png)

### 內容功能表選項

下列內容功能表選項可供使用：

| 選項 | 說明 |
|--- |--- |
| **[!UICONTROL 趨勢接觸點]** | 在折線圖中查看接觸點的趨勢資料，其中包含一些預先建立的異常偵測資料。 |
| **[!UICONTROL 趨勢接觸點 (%)]** | 總流失百分比趨勢。 |
| **[!UICONTROL 所有接觸點趨勢 (%)]** | 在同一圖表上顯示流失中所有接觸點的百分比趨勢(除了&#x200B;**[!UICONTROL 所有訪客]** （如果包含）)。 |
| **[!UICONTROL 在此接觸點劃分割槽間]** | 如果訪客繼續進入下一個接觸點，可檢視訪客在兩個接觸點 (此接觸點和下一個接觸點) 之間所做的動作。此選項會建立自由表格，顯示您的維度。 您可以取代表格的尺寸和其他元素。 例如，標示為&#x200B;**[!UICONTROL 區間：所有訪客>頁面等於任何首頁]**，並包含&#x200B;**[!UICONTROL 頁面]**&#x200B;作為維度，以及以&#x200B;**[!UICONTROL 僅限專案的快速區段]**&#x200B;分割的[獨特訪客](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL 區間：所有訪客>頁面等於任何首頁]**&#x200B;作為量度。 檢查區段以瞭解如何決定遞補區段。 |
| **[!UICONTROL 此接觸點的劃分流失]** | 檢視未透過funnel的訪客，在選定步驟後立即做了什麼事。 此選項會建立自由表格，顯示您的維度。 您可以取代表格的尺寸和其他元素。 例如，標示為&#x200B;**[!UICONTROL 流失：所有訪客>頁面等於任何首頁]**，並包含&#x200B;**[!UICONTROL 頁面]**&#x200B;作為維度，以及以&#x200B;**[!UICONTROL 僅限專案的快速區段]** [流失：所有訪客>頁面等於任何首頁](/help/components/segmentation/segmentation-workflow/seg-quick.md)區段作為量度的分段&#x200B;**[!UICONTROL 獨特訪客]**。 檢查區段以瞭解如何判斷流失區段。 |
| **[!UICONTROL 從接觸點建立區段]** | 從選取的接觸點建立新的區段。 |

>[!MORELIKETHIS]
>
>[將視覺化新增至面板](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[視覺效果設定](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[視覺化內容選單](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

