---
description: 此功能進一步整合 Report Builder 在一般 Excel 工作流程中的用途，讓您無須存取 Report Builder 使用者介面。
title: 從 Microsoft Excel 函數叫用 Report Builder 功能
topic: Report builder
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 從 Microsoft Excel 函數叫用 Report Builder 功能

此功能進一步整合 Report Builder 在一般 Excel 工作流程中的用途，讓您無須存取 Report Builder 使用者介面。

例如，您可能想要自動重新整理Report Builder請求，其輸入篩選是根據從其他來源提取的Excel資料。 您現在可以使用字串RefreshRequestsInCellsRange(..)來執行此動作函式。 所有呼叫都是非同步的。 它們會立即返回，而不會等待呼叫完全執行。

>[!NOTE] 您必須安裝 Report Builder 5.0 (或更高版本)，才能使用此功能。

下表列出各種公開函數：

| 函式名稱 | 說明 |
|---|---|
| 字串AsyncRefreshAll() | 重新整理活頁簿中顯示的所有報告建立工具請求。 |
| 字串AsyncRefreshRange(string rangeAddressInA1Format) | 重新整理指定儲存格範圍位址（以A1格式表示儲存格範圍的字串運算式，例如「Sheet1!A2:A10」）中顯示的所有報告建立工具請求。 |
| 字串AsyncRefreshRangeAltTextParam() | 重新整理指定儲存格範圍中，透過Ms表單控制項的替代文字顯示的所有報告建立工具請求。 |
| 字串AsyncRefreshActiveWorksheet() | 重新整理作用中工作表中顯示的所有報告建立工具請求。 |
| 字串AsyncRefreshWorksheet(string worksheetName) | 重新整理指定工作表中顯示的所有報告建立工具請求（工作表名稱，如標籤上所示）。 |
| 字串AsyncRefreshWorksheetAltTextParam(); | 重新整理特定工作表名稱中顯示的所有報告建立工具請求，這些請求是透過Ms表單控制項的替代文字傳遞的 |
| 字串GetLastRunStatus() | 傳回描述上次執行狀態的字串。 |

若要在報告建立工具中存取這些功能，請前往 [!UICONTROL Formulas] > [!UICONTROL Insert Function]。 在類別清單的底部，您會找到Adobe.ReportBuilder.Bridge:

![](assets/arb_functions.png)

## 在公式中使用這些函數 {#section_034311081C8D4D7AA9275C1435A087CD}

例如，公式

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

顯示「如果儲存格P5中的值是文字或空白，請重新整理儲存格P9中的範圍。」

## 搭配使用 Report Builder 函數與格式控制項 {#section_26123090B5BD49748C8D8ED7A1C5ED84}

您現在可以將巨集指派給您建立的控制項，而該控制項可以是重新整理活頁簿請求的函式。 例如，函式AsyncRefreshActiveWorksheet會重新整理工作表中的所有請求。 不過，有時您可能只想重新整理某些要求，而非全部。

1. 設定宏參數。
1. 按一下右鍵控制項並選擇 **[!UICONTROL Assign Macro]**。
1. 輸入 Report Builder 函數名稱 (不包含參數及括號)。

![](assets/assign_macro.png)

## 透過格式控制項將參數傳遞到 Report Builder 函數 {#section_ECCA1F4990D244619DFD79138064CEF0}

採用參數的兩個函數可與「格式控制項」搭配使用，但只能透過「替代文字」欄位：

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet（字串worksheetName）

1. 按一下右鍵控制項並選擇 **[!UICONTROL Format Control]**。

   ![](assets/format_control.png)

1. Click the [!UICONTROL Alt Text] tab.

   ![](assets/alt_text.png)

1. Under [!UICONTROL Alternative text], enter the cell range that you want refreshed.
1. 在> [!UICONTROL Formulas] >下開啟報告建立工具參數清單 [!UICONTROL Insert Function][!UICONTROL Adobe.ReportBuilder.Bridge]。

1. Pick one of the two functions that end with AltTextParam and click **[!UICONTROL OK]**.

