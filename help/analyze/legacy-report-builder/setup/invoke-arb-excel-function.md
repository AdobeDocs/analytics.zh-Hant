---
description: 瞭解如何將Microsoft Excel與Report Builder功能搭配使用，而不存取Report Builder使用者介面。
title: 瞭解如何搭配Report Builder函式使用Microsoft Excel
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
TQID: https://experienceleague.adobe.com/cgDjTqGH0KzSrpg66sRfF8Kf81Q-WDwSWJ-OBvJK8DM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 11%

---

# 搭配Microsoft Excel使用Report Builder函式

{{legacy-arb}}

您可以使用Report Builder函式來存取功能，而不需要存取Report Builder使用者介面。

例如，若要根據從其他來源提取至Excel的資料，以輸入篩選器自動重新整理Report Builder請求，請使用字串RefreshRequestsInCellsRange(..) 函式。 所有呼叫皆非同步，且會立即傳回，不會等待完全執行。

**需求**

* 需要Report Builder 5.0 （或更新版本）。

下表列出公開的函式。

| 函式名稱 | 類型 | 說明 |
|:---| --- | ---|
| AsyncRefreshAll() | 字串 | 重新整理活頁簿中存在的所有Report Builder請求。 |
| AsyncRefreshRange(string rangeAddressInA1Format) | 字串 | 重新整理指定儲存格範圍位址中存在的所有Report Builder要求（代表A1格式儲存格範圍的字串運算式，例如「Sheet1！A2:A10」）。 |
| AsyncRefreshRangeAltTextParam() | 字串 | 重新整理指定儲存格範圍中存在的所有Report Builder請求，這些請求會透過Ms表單控制項的替代文字傳遞。 |
| AsyncRefreshActiveWorksheet() | 字串 | 重新整理作用中工作表中存在的所有Report Builder請求。 |
| AsyncRefreshWorksheet(string worksheetName) | 字串 | 重新整理指定工作表中存在的所有Report Builder請求（工作表名稱出現在頁簽上）。 |
| AsyncRefreshWorksheetAltTextParam()； | 字串 | 重新整理透過Ms表單控制項的替代文字傳遞的特定工作表名稱中存在的所有Report Builder請求 |
| 字串GetLastRunStatus() | 字串 | 傳回說明上次執行狀態的字串。 |

若要存取Report Builder函式，請移至&#x200B;**[!UICONTROL 公式]** > **[!UICONTROL 插入函式]**。 使用搜尋欄位來搜尋函式，或選取類別以列出該類別中的函式。

![熒幕擷圖顯示[插入函式]視窗，類別清單已展開。](assets/arb_functions.png)

## 範例 {#section_034311081C8D4D7AA9275C1435A087CD}

下列範例顯示&#x200B;*如果儲存格P5中的值為文字或空白，請重新整理儲存格P9*&#x200B;中的範圍。

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## 搭配使用Report Builder函式與格式控制項 {#section_26123090B5BD49748C8D8ED7A1C5ED84}

您可以將巨集指派給您建立的控制項，而控制項可以是重新整理活頁簿請求的函式。 例如，函式AsyncRefreshActiveWorksheet將重新整理工作表中的所有請求。 不過，有時您可能只想重新整理某些請求。

1. 設定巨集引數。
1. 在控制項上按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 「指定巨集」]**。
1. 輸入Report Builder函式名稱（不含引數或括弧）。

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
1. 在&#x200B;**[!UICONTROL 公式]** > **[!UICONTROL 插入函式]**> **[!UICONTROL Adobe.ReportBuilder.Bridge]**&#x200B;下開啟Report Builder引數清單。

1. 從兩個函數中選擇結尾是 AltTextParam 的函數，然後按一下&#x200B;**[!UICONTROL 「確定」]**。
