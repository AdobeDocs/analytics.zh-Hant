---
description: 顯示特定維的下一個或上一個維項的面板。
title: 下一個或上一個項目面板
feature: Panels
role: User, Admin
source-git-commit: d4106324f6716139731cc6bd948ef06b35303620
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 8%

---


# 下一個或上一個項目面板

的 [!UICONTROL 下一項或上一項] 面板以報告和分析中的報告形式開始，位於 [!UICONTROL 報告] > [!UICONTROL 最受歡迎] > [!UICONTROL 下一頁/上一頁]。 此「工作區」面板包含許多表和可視化，可輕鬆標識特定維的下一個或上一個維項。 例如， 
        

## 訪問面板

您可以從中訪問面板 [!UICONTROL 報告] 或 [!UICONTROL 工作區]。

| 接入點 | 說明 |
| --- | --- |
| [!UICONTROL 報表] | <ul><li>該面板已放入項目中。</li><li>左滑軌已折疊。</li><li>如果已選擇 [!UICONTROL 下一頁]，已應用預設設定，如 [!UICONTROL 頁面] 為 [!UICONTROL Dimension]，以及 [!UICONTROL Dimension項]。 [!UICONTROL 下一個] 為 [!UICONTROL 方向] 和 [!UICONTROL 訪問] 為 [!UICONTROL 容器]。 您可以修改所有這些設定。</li></ul>![下一/上一面板](assets/next-previous.png) |
| Workspace | 建立新項目並選擇左滑軌中的「面板」表徵圖。 然後拖動 [!UICONTROL 下一項或上一項] 的子菜單。 請注意 [!UICONTROL Dimension] 和 [!UICONTROL Dimension項] 欄位留空。 從下拉清單中選擇一個維。 [!UICONTROL Dimension項] 根據 [!UICONTROL 尺寸] 你選擇了。 將添加頂部維項，但可以選擇其他項。 預設值為「Next（下一步）」和「Visitor（訪問者）」。 同樣，您也可以修改這些。<p>![下一/上一面板](assets/next-previous2.png) |

{style=&quot;table-layout:auto&quot;}

## 面板輸入 {#Input}

您可以配置 [!UICONTROL 下一項或上一項] 使用這些輸入設定的面板面板：

| 設定 | 說明 |
| --- | --- |
| 段（或其他元件）下拉區域 | 可以拖放段或其他元件以進一步篩選面板結果。 |
| 維度 | 要瀏覽下一個或上一個項的維。 |
| 維度項目 | 下次/上一次查詢中心的特定項目。 |
| 方向 | 指定是否正在查找 [!UICONTROL 下一個] 或 [!UICONTROL 上一個] 維項。 |
| 容器 | [!UICONTROL 訪問] 或 [!UICONTROL 訪問者] （預設）確定查詢範圍。 |

{style=&quot;table-layout:auto&quot;&quot;

按一下 **[!UICONTROL 生成]** 來構建面板。

## 面板輸出 {#output}

的 [!UICONTROL 下一項或上一項] 面板返回一組豐富的資料和可視化效果，以幫助您更好地瞭解特定維項後面或之前出現的事件。

![下一/上一面板輸出](assets/next-previous-output.png)

![下一/上一面板輸出](assets/next-previous-output2.png)

| 視覺效果 | 說明 |
| --- | --- |
| 橫條圖 | 根據您選擇的維項列出下一個（或上一個）項。 懸停在單個條上時，將加亮「自由形式」(Freeform)表格中的相應項。 |
| 摘要數字 | 當前月份（到目前為止）所有下一個或上一個維項目的高級匯總編號。 |
| 自由表格 | 以表格格式根據所選維項列出下一個（或上一個）項。 例如，這些頁是人們在首頁或工作區頁面之後（或之前）訪問的最熱門的頁面（按具體值）。 |

{style=&quot;table-layout:auto&quot;&quot;
