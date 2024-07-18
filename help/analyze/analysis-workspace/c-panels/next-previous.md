---
description: 顯示特定維度的下一個或上一個維度專案的面板。
title: 下一個或上一個項目面板
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 5%

---

# 下一個或上一個項目面板

此面板包含許多表格和視覺效果，可輕鬆識別特定維度的下一個或上一個維度專案。 例如，您可能會想要探索客戶在造訪首頁後最常前往哪些頁面。

## 存取面板

您可以從[!UICONTROL 報表]內或[!UICONTROL Workspace]記憶體取面板。

| 存取點 | 說明 |
| --- | --- |
| [!UICONTROL 報表] | <ul><li>該面板已放入專案中。</li><li>左側邊欄會摺疊。</li><li>若您選取[!UICONTROL 下一頁]，已套用預設設定，例如[!UICONTROL Dimension]的[!UICONTROL 頁面]，且最上層頁面為[!UICONTROL Dimension專案]、[!UICONTROL 方向]的[!UICONTROL 下一頁]以及[!UICONTROL 容器]的[!UICONTROL 造訪]。 您可以修改所有這些設定。</li></ul>![下一個/上一個面板](assets/next-previous.png) |
| Workspace | 建立新專案，並在左側欄中選取「面板」圖示。 然後將[!UICONTROL 下一個或上一個專案]面板拖曳到自由表格上方。 請注意，[!UICONTROL Dimension]和[!UICONTROL Dimension專案]欄位保留空白。 從下拉式清單中選取維度。 已根據您選擇的[!UICONTROL 維度]填入[!UICONTROL Dimension專案]。 系統會新增排名最前的維度專案，但您可以選取其他專案。 預設值為「下一個」和「訪客」。 同樣地，您也可以修改這些內容。<p>![下一個/上一個面板](assets/next-previous2.png) |

{style="table-layout:auto"}

## 面板輸入 {#Input}

您可以使用這些輸入設定來設定[!UICONTROL 下一個或上一個專案]面板面板：

| 設定 | 說明 |
| --- | --- |
| 區段（或其他元件）拖放區域 | 您可以拖放區段或其他元件以進一步篩選面板結果。 |
| 維度 | 您要探索下一個或上一個專案的維度。 |
| 維度項目 | 您下次/上次查詢中心的特定專案。 |
| 方向 | 指定您要尋找[!UICONTROL Next]或[!UICONTROL Previous]維度專案。 |
| 容器 | [!UICONTROL 造訪]或[!UICONTROL 訪客] （預設）決定您的查詢範圍。 |

{style="table-layout:auto"}

按一下&#x200B;**[!UICONTROL 建置]**&#x200B;以建置面板。

## 面板輸出 {#output}

[!UICONTROL 下一個或上一個專案]面板會傳回一組豐富的資料和視覺效果，協助您更清楚瞭解特定維度專案之後或之前的情形。

![下一個/上一個面板輸出](assets/next-previous-output.png)

![下一個/上一個面板輸出](assets/next-previous-output2.png)

| 視覺效果 | 說明 |
| --- | --- |
| 橫條圖 | 根據您選擇的維度專案列出下一個（或上一個）專案。 將滑鼠懸停在個別長條上，會醒目顯示自由格式表格中的對應專案。 |
| 摘要數字 | 目前月份（到目前為止）所有下一個或上一個維度專案發生次數的高層級摘要數字。 |
| 自由表格 | 根據您選擇的維度專案，以表格格式列出下一個（或上一個）專案。 例如，在首頁或Workspace頁面之後（或之前），人們最常前往的頁面（依發生次數而定）。 |

{style="table-layout:auto"}
