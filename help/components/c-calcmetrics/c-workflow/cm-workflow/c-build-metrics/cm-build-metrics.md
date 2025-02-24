---
description: 計算量度產生器提供的畫布可用來拖放維度、量度、區段及函數，讓您根據容器階層邏輯、規則及運算子來建立自訂量度。此整合性開發工具可讓您建立並儲存簡單的計算量度或複雜的進階計算量度。
title: 建置量度
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: eb2b5e078fdb299ed7d82fed54e98e5a40059624
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 43%

---

# 建置量度 {#build-metrics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="產品相容性"
>abstract="指出可以在 Customer Journey Analytics 的何處使用此計算量度，例如在 Analysis Workspace、Report Builder 等。一些計算量度不能用於實驗。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="在實驗中使用計算量度"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_externalid"
>title="外部 ID"
>abstract="變更外部 ID 可能會影響計算量度在外部來源 (例如商業智慧工具) 中的顯示方式"

<!-- markdownlint-enable MD034 -->

Adobe Analytics提供畫布來拖放維度、量度、區段和函式，以便根據容器階層邏輯、規則和運運算元建立自訂量度。 此整合性開發工具可讓您建立並儲存簡單或複雜的計算量度。

## 開始建立計算量度

您可以使用計算量度產生器來建立或編輯計算量度。 以這種方式建立時，計算量度會顯示在元件清單中，然後可用於整個組織的專案。 或者，您也可以建立快速計算量度，如[在[量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md)中為單一專案](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)建立計算量度中所述。

存取計算量度產生器，以開始建立元件清單中可用的計算量度。

1. 以下列任何方式存取計算量度產生器：

   * 在Analysis Workspace中，開啟專案，然後選取&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 建立量度]**。
   * 在Analysis Workspace中，開啟專案，然後選取左側邊欄中&#x200B;[!UICONTROL **量度**]&#x200B;區段旁的&#x200B;**加號**&#x200B;圖示。
   * 在[!DNL Adobe Analytics]中，移至&#x200B;**[!UICONTROL 元件]** > **[!UICONTROL 計算量度]**，然後選取計算量度頁面頂端的&#x200B;**[!UICONTROL +新增]**。

1. 繼續使用計算量度產生器](#areas-of-the-calculated-metrics-builder)的[區域。

## 計算量度產生器的區域

下圖及隨附表格說明計算量度產生器的部分主要區域和功能。

![](assets/cm_builder_ui.png)

| 影像中的位置 | 名稱與功能 |
|---|---|
| 1 | **標題：**&#x200B;必須為量度命名。 未命名的量度將無法儲存。 |
| 2 | **描述：**&#x200B;提供使用者易記的描述，以顯示其用途並與類似用途區分開來。 <p>此說明也會顯示在報表中。最好「不要」在說明中加入公式，而是該說明此量度適合和不適合的用途。(公式會在您建立量度時產生，位在「摘要」標頭下方。因此無需將公式加入說明中。) </p> |
| 3 | **格式：**&#x200B;選項包括「小數」、「時間」、「百分比」和「貨幣」。 |
| 4 | **小數位數：**&#x200B;顯示報告中將顯示多少小數位數。 您可指定的小數位數上限為 10。 |
| 5 | **顯示上升趨勢的方式：**&#x200B;此量度極性設定會顯示Analytics應將量度的上升趨勢視為好（綠色）或壞（紅色）。 因此，報表的圖形會隨著量度上升而顯示為綠色或紅色。 |
| 6 | **標籤：**&#x200B;標籤是組織量度的好方法。 所有使用者都能建立標記，並套用一或多個標記至量度。不過，您僅可以看見自己所擁有或已共用給您之區段的標記。您應該建立什麼樣的標記？以下是一些建議的實用標記：<ul><li>**團隊名稱**，例如社交行銷、行動行銷。</li><li>**專案** （分析標籤），例如登入頁面分析。</li><li>**類別**，例如「女性」；「地理」。</li><li>**工作流程**，例如「待核准」、策劃（特定的業務單位）</li></ul> |
| 7 | **摘要：** <p>「摘要」公式會隨著您變更量度定義而更新。 當您將滑鼠游標停留在量度上並按一下「 」，此公式也會顯示在量度邊欄中。 <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />圖示。 </p> |
| 8 | **定義：**&#x200B;您可在此拖曳量度/計算量度、區段及/或函式，以建立計算量度。 <ul><li>如果您將一個計算量度拖曳進來，它將自動展開其量度定義。 </li> <li>您可以使用容器巢狀嵌套定義。不過，這些容器與區段容器不同，其功能比較類似數學運算式，用以決定運算順序。 </li> </ul> |
| 9 | **運運算元：**&#x200B;除以( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> )為預設運運算元，另外還有+、 — 和x運運算元。 |
| 10 | **預覽：**&#x200B;針對任何可能的錯誤提供快速閱讀。 預覽涵蓋最近 90 天。這可供您初步衡量是否為量度選擇了正確的元件。意外的結果可能表示您需要再次檢查量度定義。 |
| 11 | **產品相容性：**&#x200B;產品相容性會顯示量度是否與<a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html"  >目前的資料</a>、完全處理的資料相容，或僅與行銷管道報表（首次接觸配置）相容。 <p>附註：目前的資料並未支援所有量度。包含區段或函數的量度與目前的資料不相容。<a href="/help/components/c-calcmetrics/cm-compatibility.md"  > 更多... </a> </p> </p> |
| 12 | **新增：**&#x200B;對於所有型別的計算量度，您可以將容器和靜態數字新增到定義中。 若為進階計算量度，您也可以新增區段和函數。 <ul><li>容器的功能類似數學運算式，用以決定運算順序。所以容器中的項目會先行處理，再進行下一個運算。</li><li>拖曳區段至容器可分割該容器中的項目。(僅限進階計算量度)</li><li>您可以在容器中堆疊多個區段。</li></ul> |
| 13 | **齒輪圖示（量度型別、歸因）：**&#x200B;選取量度旁的齒輪圖示，即可指定<a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  >量度型別和歸因模型</a>。 |
| 14 | **新增：**&#x200B;可讓您建立新元件，例如新區段（會帶您前往<a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  >區段產生器</a>）。 |
| 15 | **搜尋元件：**&#x200B;此搜尋列可讓您搜尋維度、量度、區段（僅限進階計算量度）和函式（僅限進階計算量度）。 |
| 16 | **維度清單：**&#x200B;您可以將「頁面」拖曳進來，並直接從計算量度產生器選取「首頁」，而不用為了在區段產生器中建立簡易區段（例如「頁面=首頁」）而離開計算量度產生器。<p>如此將可讓工作流程更為流暢，方便建立區段計算量度。</p> |
| 17 | **量度清單：**&#x200B;量度共有3個類別： <ul> <li>標準量度(<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>計算量度( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">量度範本( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />) — 在清單底部。 </li> </ul> <p>當您將游標停留在量度上時，其右側會顯示資訊圖示： <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />。按一下此圖示會提供下列資訊： </p><ul> <li>其計算公式。 </li><li>量度的預覽趨勢。 </li><li>編輯（鉛筆）圖示 <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" />位於右上方，帶您前往計算量度產生器以編輯此計算量度。 </li></ul> |
| 18 | **區段清單：** （僅限進階計算量度）身為管理員，此清單會顯示在您的登入公司中建立的所有區段。 如果您不是管理員使用者，此清單會顯示您擁有以及與您共用的區段。<a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html"  > 更多... </a> |
| 19 | **函式清單：** （僅限進階計算量度）函式分為兩個清單： <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  >基本</a> （最常使用）和<a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  >進階</a>。 |
| 20 | **報表套裝選取器：**&#x200B;可讓您切換至不同的報表套裝。 |

{style="table-layout:auto"}
