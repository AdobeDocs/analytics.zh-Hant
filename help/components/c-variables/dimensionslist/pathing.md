---
description: 一組基於路徑分析的報告。 從技術上講，路徑分析是指從一個頁面名稱移至另一個頁面名稱（從一個值移至另一個值）。
title: 路徑分析
topic: Reports
uuid: c4ff9fa8-e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 路徑分析

一組基於路徑分析的報告。 從技術上講，路徑分析是指從一個頁面名稱移至另一個頁面名稱（從一個值移至另一個值）。

[Analysis Workspace 流量](https://marketing.adobe.com/resources/help/zh_TW/analytics/analysis-workspace/flow.html)可提供更具彈性的路徑選項。

>[!NOTE] 若要啟用路徑功能，請前往 **[!UICONTROL Admin > Report Suites > Edit Settings > Traffic > Traffic Variables]**。 若要在「網站區域」及「伺服器」報表啟用路徑功能，請聯絡客戶服務。

如果您需要知道值的收集順序，則需要為收集這些值的變數啟用路徑分析。 依預設會為頁面啟用路徑功能。 依預設，路徑分析不會為任何prop啟用，因為它僅適用於特定情況。 請連絡客戶服務以啟用prop的路徑分析。

>[!NOTE] 在 Ad Hoc Analysis 中，當您對 prop 啟用分類時，為已啟用的 prop 所設定的所有分類，都可使用路徑量度。

**範例——網站區域的路徑分析**

Enabling pathing for the *`s.channel`* variable allows you to track how site visitors move between Site Sections (as the value changes).

![](assets/path_sections.png)

然後，路徑分析便可用於各種路徑報表， [!UICONTROL Next Site Section Flow]例如顯示訪客在頁面群組或網站區段間的移動方式。

![](assets/paths_report.png)

**範例——搜尋的路徑**

這種從一個值移至另一個值的相同概念也可套用至其他流量變數，包括 *`s.props`*。例如，如果為內部搜尋詞 *`s.prop`* 啟用路徑功能，便可查看訪客透過搜尋詞所使用的路徑。

**範例——每個登入狀態的路徑**

您可能想要根據訪客的登入狀態，瞭解訪客在您網站中的路徑。 若要查看此資訊，您不會查看路徑報表的登入狀態，因為這些報表會顯示訪客如何變更該報表中的值，或訪客如何從登入變更為登出。 請改為串連區段值與變數，然 *`s.pageName`* 後連結結果變數的路徑。 以下是根據成員狀態來建立頁面路徑的範例程式碼：

```js
s.pageName="Home Page"; 
s.prop18="Gold"; // Member Status 
s.prop19=s.prop18 + ":" + s.pageName;
```

然後，啟用路徑功 *`s.prop19`* 能，以查看成員在頁面間的路徑。

>[!NOTE] 若您執行 Ad Hoc Analysis，則可直接將頁面路徑分段而無需連結區段值，然後對路徑報表套用任何區段。

