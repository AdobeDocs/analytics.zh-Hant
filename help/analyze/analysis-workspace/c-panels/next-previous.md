---
description: 顯示特定維度的下一個或上一個維度項目的面板。
title: 下一個或上一個項目面板
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: c289f4aa1e49e428182fed9a871a1f90dd1f5c42
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---

# 下一個或上一個項目面板

此 [!UICONTROL 下一個或上一個項目] 面板起始為「Reports &amp; Analytics」下方的報表 [!UICONTROL 報表] > [!UICONTROL 最受歡迎] > [!UICONTROL 下一頁/上一頁]. 現在也是「工作區」面板。 此面板包含許多表格和視覺效果，可輕鬆識別特定維度的下一個或上一個維度項目。 例如，您可能想要探索客戶造訪首頁後最常前往的頁面。

## 存取面板

您可以從中存取面板 [!UICONTROL 報表] 或 [!UICONTROL 工作區].

| 接入點 | 說明 |
| --- | --- |
| [!UICONTROL 報表] | <ul><li>面板已放入專案中。</li><li>左側邊欄已收合。</li><li>如果您選取 [!UICONTROL 下一頁]，則已套用預設設定，例如 [!UICONTROL 頁面] for [!UICONTROL Dimension]，而頂端頁面為 [!UICONTROL Dimension項目], [!UICONTROL 下一個] for [!UICONTROL 方向] 和 [!UICONTROL 瀏覽] for [!UICONTROL 容器]. 您可以修改所有這些設定。</li></ul>![下一個/上一個面板](assets/next-previous.png) |
| Workspace | 建立新專案並選取左側邊欄中的「面板」圖示。 然後拖曳 [!UICONTROL 下一個或上一個項目] 表格上方的面板。 請注意， [!UICONTROL Dimension] 和 [!UICONTROL Dimension項目] 欄位留空。 從下拉式清單中選取維度。 [!UICONTROL Dimension項目] 會根據 [!UICONTROL 維度] 你選了。 會新增排名在前的維度項目，但您可以選取不同的項目。 預設值為「下一個」和「訪客」。 同樣地，您也可以修改這些項目。<p>![下一個/上一個面板](assets/next-previous2.png) |

{style="table-layout:auto"}

## 面板輸入 {#Input}

您可以設定 [!UICONTROL 下一個或上一個項目] 使用下列輸入設定的面板面板：

| 設定 | 說明 |
| --- | --- |
| 區段（或其他元件）拖放區域 | 您可以拖放區段或其他元件，以進一步篩選面板結果。 |
| 維度 | 您要探索下一個或前一個項目的維度。 |
| Dimension項目 | 下次/上次查詢中心的特定項目。 |
| 方向 | 指定您是否要尋找 [!UICONTROL 下一個] 或 [!UICONTROL 上一個] 維度項目。 |
| 容器 | [!UICONTROL 瀏覽] 或 [!UICONTROL 訪客] （預設）決定查詢範圍。 |

{style="table-layout:auto"}

按一下 **[!UICONTROL 建置]** 來建立面板。

## 面板輸出 {#output}

此 [!UICONTROL 下一個或上一個項目] 面板會傳回一組豐富的資料和視覺效果，協助您更清楚了解特定維度項目之後或之前的發生次數。

![下一個/上一個面板輸出](assets/next-previous-output.png)

![下一個/上一個面板輸出](assets/next-previous-output2.png)

| 視覺效果 | 說明 |
| --- | --- |
| 橫條圖 | 根據您選擇的維度項目列出下一個（或上一個）項目。 將滑鼠指標暫留在個別列上時，會反白標示自由表格中的對應項目。 |
| 摘要數字 | 當月（至今）所有下一個或上一個維度項目發生次數的高階摘要數。 |
| 自由表格 | 根據您選擇的維度項目，以表格格式列出下一個（或上一個）項目。 例如，哪些是人們在首頁之後（或之前）或工作區頁面前往的最受歡迎頁面（依發生次數）。 |

{style="table-layout:auto"}
