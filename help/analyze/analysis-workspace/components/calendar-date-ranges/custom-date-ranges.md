---
description: 在 Analysis Workspace 中建立自訂日期範圍，並將其儲存為時間元件。
keywords: Analysis Workspace
title: 建立自訂日期範圍
uuid: c8873d41-454d-4f22-ad1f-38cacec5a3bc
feature: Workspace Basics
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 100%

---


# 建立自訂日期範圍

在 Analysis Workspace 中建立自訂日期範圍，並將其儲存為時間元件。

**[!UICONTROL 元件]** > **[!UICONTROL 新的日期範圍]**

日期範圍會套用至面板層級。若要新增日期範圍至專案，請按一下&#x200B;**「面板** > *`<select panel>`*」，指定新的日期範圍。

## 「兩個月前」的日期範圍{#section_C4109C57CB444BB2A79CC8082BD67294}

下列自訂日期範圍會顯示「兩個月前」的日期範圍，而「摘要變更」視覺效果會顯示方向變化。

![](assets/date-range-two-months-ago.png)

自訂日期範圍會顯示在您專案中的「[!UICONTROL 日期範圍]」元件面板上方：

![](assets/date-range-panel-two-months-ago.png)

您可將此自訂日期範圍拖曳至使用「上個月」預設集之自訂每月滾動日期範圍旁的欄中，用以進行比較。新增「摘要變更」視覺效果並選取每個欄的總計，顯示方向變化：

![](assets/date-range-two-months-table.png)

## 使用 7 天滾動日期範圍{#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

日期範圍會套用至面板層級。若要新增日期範圍至專案，請按一下「**動作** > **新增面板**」，指定新的日期範圍。

您可以在日期範圍產生器中建立自訂日期範圍，用於和其他日期範圍一起顯示在元件面板中。

例如，您可以建立一個日期範圍，指定在一週前結束的 7 天滾動期間：

![](assets/create_date_range.png)

使用&#x200B;*`rolling daily`*。

* 開始設定是 *`current day minus 14 days`*。

* 結束設定是 *`current day minus 7 days`*。

您可將此日期範圍當做元件，拖曳至其他自由表格上。
