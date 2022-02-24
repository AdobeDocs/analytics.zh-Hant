---
description: 在 Analysis Workspace 中建立自訂日期範圍，並將其儲存為時間元件。
keywords: Analysis Workspace
title: 建立自訂日期範圍
feature: Calendar
role: User, Admin
exl-id: 586bb120-3f20-452c-9867-0b93d2e794bc
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: ht
source-wordcount: '248'
ht-degree: 100%

---

# 建立自訂日期範圍

在 Analysis Workspace 中建立自訂日期範圍，並將其儲存為時間元件。

**[!UICONTROL 元件]** > **[!UICONTROL 新的日期範圍]**

日期範圍會套用至面板層級。若要新增日期範圍至專案，請按一下&#x200B;**「面板** > *`<select panel>`*」，指定新的日期範圍。

## 「兩個月前」的日期範圍 {#section_C4109C57CB444BB2A79CC8082BD67294}

下列自訂日期範圍會顯示「兩個月前」的日期範圍，而「摘要變更」視覺效果會顯示方向變化。

![](assets/date-range-two-months-ago.png)

自訂日期範圍會顯示在您專案中的「[!UICONTROL 日期範圍]」元件面板上方：

![](assets/date-range-panel-two-months-ago.png)

您可將此自訂日期範圍拖曳至使用「上個月」預設集之自訂每月滾動日期範圍旁的欄中，用以進行比較。新增「摘要變更」視覺效果並選取每個欄的總計，顯示方向變化：

![](assets/date-range-two-months-table.png)

## 使用 7 天滾動日期範圍 {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

日期範圍會套用至面板層級。若要新增日期範圍至專案，請按一下「**動作** > **新增面板**」，指定新的日期範圍。

您可以在日期範圍產生器中建立自訂日期範圍，用於和其他日期範圍一起顯示在元件面板中。

例如，您可以建立一個日期範圍，指定在一週前結束的 7 天滾動期間：

![](assets/create_date_range.png)

使用&#x200B;*`rolling daily`*。

* 開始設定是 *`current day minus 14 days`*。

* 結束設定是 *`current day minus 7 days`*。

您可將此日期範圍當做元件，拖曳至其他自由表格上。
