---
description: 瞭解如何將Microsoft Excel與Report Builder功能搭配使用，而不存取Report Builder使用者介面。
title: 瞭解如何搭配Report Builder函式使用Microsoft Excel
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 41%

---

# 搭配Microsoft Excel使用Report Builder函式

您可以使用Report Builder函式來存取功能，而無需存取Report Builder使用者介面。

例如，若要根據從其他來源提取到Excel中的資料，以輸入篩選器自動重新整理Report Builder請求，請使用字串RefreshRequestsInCellsRange(..) function. 所有呼叫皆非同步，且會立即傳回，不會等待完全執行。

**需求**

* 需要Report Builder5.0 （或更新版本）。

下表列出公開的函式。

| 函數名稱 | 類型 | 說明 |
|:---| --- | ---|
| AsyncRefreshAll() | 字串 | 重新整理活頁簿顯示的所有 Report Builder 請求。 |
| AsyncRefreshRange(string rangeAddressInA1Format) | 字串 | 重新整理指定儲存格範圍位址 (以 A1 格式表示儲存格範圍的字串表示式，例如「Sheet1!A2:A10」) 中顯示的所有 Report Builder 請求。 |
| AsyncRefreshRangeAltTextParam() | 字串 | 重新整理指定儲存格範圍 (通過 Ms 表單控制項中的替代文字) 中顯示的所有 Report Builder 請求。 |
| AsyncRefreshActiveWorksheet() | 字串 | 重新整理使用中工作表顯示的所有 Report Builder 請求。 |
| AsyncRefreshWorksheet(string worksheetName) | 字串 | 重新整理指定工作表顯示的所有 Report Builder 請求 (工作表名稱為索引標籤上顯示的名稱)。 |
| AsyncRefreshWorksheetAltTextParam()； | 字串 | 重新整理特定工作表名稱 (通過 Ms 表單控制項中的替代文字) 中顯示的所有 Report Builder 請求。 |
| 字串GetLastRunStatus() | 字串 | 傳回說明上一次執行狀態的字串。 |

若要存取Report Builder函式，請移至&#x200B;**[!UICONTROL 公式]** > **[!UICONTROL 插入函式]**。 使用搜尋欄位來搜尋函式，或選取類別以列出該類別中的函式。

![熒幕擷圖顯示[插入函式]視窗，類別清單已展開。](assets/arb_functions.png)

## 範例 {#section_034311081C8D4D7AA9275C1435A087CD}

下列範例顯示&#x200B;*如果儲存格P5中的值為文字或空白，請重新整理儲存格P9*&#x200B;中的範圍。

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## 搭配使用Report Builder函式與格式控制項 {#section_26123090B5BD49748C8D8ED7A1C5ED84}

您可以將巨集指派給您建立的控制項，而控制項可以是重新整理活頁簿請求的函式。 例如，函數 AsyncRefreshActiveWorksheet 會重新整理工作表中的所有請求。不過，有時您可能只想重新整理某些請求。

1. 設定巨集參數。
1. 在控制項上按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 「指定巨集」]**。
1. 輸入Report Builder函式名稱（無引數或括弧）。

![顯示[指派巨集]視窗的熒幕擷圖。](assets/assign_macro.png)

## 使用格式控制項將引數傳遞至Report Builder函式 {#section_ECCA1F4990D244619DFD79138064CEF0}

採用引數的兩個函式可搭配「格式控制項」使用。 您必須使用&#x200B;**替代文字：**&#x200B;欄位：

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

若要使用格式控制項將引數傳遞至Report Builder函式

1. 在控制項上按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 「格式控制項」]**。

   ![熒幕擷圖顯示選取的格式控制項。](assets/format_control.png)

1. 按一下&#x200B;**[!UICONTROL 「替代文字」]**&#x200B;索引標籤。

   ![顯示[替代文字]索引標籤和[替代文字]欄位的熒幕擷圖。](assets/alt_text.png)

1. 在&#x200B;**[!UICONTROL 「替代文字」]**&#x200B;下，輸入您要重新整理的儲存格範圍。
1. 在&#x200B;**[!UICONTROL 公式]** > **[!UICONTROL 插入函式]**> **[!UICONTROL Report Builder.Adobe.Bridge]**&#x200B;下開啟ReportBuilder引數清單。

1. 從兩個函數中選擇結尾是 AltTextParam 的函數，然後按一下&#x200B;**[!UICONTROL 「確定」]**。
