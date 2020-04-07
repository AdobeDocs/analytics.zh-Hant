---
description: 'null'
title: 設定流失視覺效果
uuid: fc117745-baf3-46fb-873d-9307092cc337
translation-type: tm+mt
source-git-commit: 2cd9872ed5052b9569d03a07d5171221b9e0af29

---


# 設定流失視覺效果

您可以指定觸點以建立多維度流失序列。 通常，觸點是您網站上的頁面。 但接觸點不限於頁面。 例如，您可以新增事件，例如單位，以及獨特訪客和回訪。 您也可以新增維度，例如類別、瀏覽器類型或內部搜尋詞。

您甚至可以在接觸點中新增區段。 例如，您可能想要比較區段，例如iOS和Android使用者。 將所要的區段拖曳至流失頂端，這些區段的相關資訊會新增至流失報表。 如果您只想顯示這些區段，可以移除「所有瀏覽」基線。

您可以新增的步驟數或使用的維度數目沒有限制。

您可以對eVar進行路徑分析，包括銷售eVar和 [listVar](https://marketing.adobe.com/resources/help/zh_TW/sc/implement/listN.html) （每個點擊可以有多個值的變數，例如產品、listVar、銷售eVar和清單prop）。 舉例來說，假設某人正在同一頁面上查看鞋子和上衣，而在下一頁改為查看上衣和襪子。下一份來自鞋類的產品流量報告將是襯衫和襪子，而非襯衫。

1. 從「視 [!UICONTROL Fallout] 覺化」下拉式清單拖曳視覺化至 [!UICONTROL Freeform Table]。

1. Drag the Page dimension into the Freeform Table and from there, drag a page (in this case, Home - JJEsquire) into the **[!UICONTROL Add TouchPoint]** field as the first touchpoint.

   ![](assets/fallout1.png)

   將滑鼠移到接觸點上方，查看流失和該層級的其他相關資訊，例如接觸點的名稱、該點的訪客計數，並可查看該接觸點的成功率 (以及比較其他接觸點的成功率)。

   橫條灰色部分的圈數顯示接觸點之間的流失（而非該點的整體流失）。 「接觸點百分比」顯示流失報表中從上一個步驟到目前步驟的成功落差。

   您也可以新增單一頁面至流失報表，而非整個維度。 按一下頁面維度上的向右箭頭「>」，選取要新增至流失報表的特定頁面。

1. 繼續新增觸點，直到序列完成為止。

   您可以將 **一或多個其他觸點拖曳** 至一個觸點，以結合多個觸點。

   >[!NOTE]
   >
   >多個區段必須以 AND 連結，但多個項目 (例如維度項目和量度) 則須以 OR 連結。

   ![](assets/multiple_obj_touchpoint.png)

1. You can also **constrain individual touchpoints to the next hit** (as opposed to &quot;eventually&quot;) within the path. 在各接觸點下方，為含有「最終路徑」和「下一次點擊」選項的選擇器，如下所示：

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>最終路徑 </p> <p>(預設) </p> </td> 
   <td colname="col2"> <p>訪客會被計算為「最終」著陸於路徑的下一頁，但不一定是在下次點擊時。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>下次點擊 </p> </td> 
   <td colname="col2"> <p>訪客會被計算為會在下一次點擊的路徑的下一頁著陸。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 流失設定 {#section_0C7C89D72F0B4D6EB467F278AC979093}

| 設定 | 說明 |
|--- |--- |
| 流失容器 <ul><li>瀏覽</li><li>訪客</li></ul> | 可讓您切換瀏覽和訪客，分析訪客路徑。預設為「訪客」。這些設定可協助您了解訪客層級的訪客參與程度 (跨越造訪)，或是將分析限制在單一造訪。 |
| 將「所有訪客」顯示為第一個接觸點 | 如果您不想將「所有訪客」顯示為第一個接觸點，您可以取消選取此項。 |

**以滑鼠右鍵按一下接觸點**，下列選項就會出現：

| 選項 | 說明 |
|--- |--- |
| 趨勢觸點 | 檢視折線圖中某個觸點的趨勢資料，以及一些預先建立的異常偵測資料。 |
| 趨勢觸點(%) | 追蹤流失總百分比。 |
| 趨勢化所有觸點(%) | 將流失中所有觸點百分比(「所有瀏覽」（如果包含的話）趨勢化為相同圖表。 |
| 在此觸點劃分落差 | 檢視訪客在兩個觸點（此觸點和下一個觸點）之間所做的動作（如果他們繼續進入下一個觸點）。 這會建立自由表格，顯示您的維度。 可替換表的尺寸和其他元素。 |
| 在此觸點劃分流失 | 檢視未透過漏斗的人員在選取步驟後立即執行的動作。 |
| 從觸點建立區段 | 從選取的接觸點建立新區段。 |
