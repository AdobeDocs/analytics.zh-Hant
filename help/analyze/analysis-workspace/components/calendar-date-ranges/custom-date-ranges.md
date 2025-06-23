---
description: 在 Analysis Workspace 中建立自訂日期範圍，並將其儲存為時間元件。
keywords: Analysis Workspace
title: 建立自訂日期範圍
feature: Date Ranges
role: User, Admin
exl-id: 586bb120-3f20-452c-9867-0b93d2e794bc
source-git-commit: 1281bdc569c9ebc5d8daa151b19dc21710633eab
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 100%

---

# 建立自訂日期範圍

您可以在 Analysis Workspace 中建立自訂日期範圍，並將其儲存為時間元件。

如需有關新增現有日期範圍至專案的資訊，請參閱[行事曆和日期範圍概觀](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md)。

若要建立自訂日期範圍：

1. 在 Adobe Analytics 中，選取「**[!UICONTROL 元件]**」>「**[!UICONTROL 日期範圍]**」。

   ![日期範圍頁面](assets/date-ranges.png)

1. 請選取「[!UICONTROL **建立新的日期範圍**]」。

1. 在日期範圍建立工具中，指定以下資訊：

   | 選項 | 說明 |
   |---------|----------|
   | [!UICONTROL **標題**] | 當使用者在 Analysis Workspace 中選取日期範圍時，會顯示此日期範圍的標題。 |
   | [!UICONTROL **說明**] | 日期範圍的說明。 |
   | [!UICONTROL **標記**] | 您想要套用於此日期範圍的任何標記。 |
   | [!UICONTROL **日期範圍**] | 可讓您挑選自訂日期範圍。根據預設，已選取最近 30 天。 |
   | [!UICONTROL **預設集**] | 從預設的日期範圍清單中選擇，例如&#x200B;[!UICONTROL **昨天**]、[!UICONTROL **最近 7 天**]、[!UICONTROL **最近 30 天**]&#x200B;等等。 |
   | [!UICONTROL **開始時間**] | 日期範圍開始之日的時間。 |
   | [!UICONTROL **結束時間**] | 日期範圍結束日的時間。 |
   | [!UICONTROL **使用滾動日期**] | 您可以使用滾動日期，根據執行報告的時間來產生動態報告，往前或往後查看一段時間的情況。舉例來說，如果您想在報表中加入「上個月」所下的所有「訂單」資料 (以「已建立日期」欄位為依據) 並在 12 月執行報表運算，您就會在報表中看到 11 月下的訂單。如果在 1 月執行相同報表運算，則會看到在 12 月下的訂單。<ul><li>**[!UICONTROL 日期預覽]**：指出滾動日曆包含的時間期間。</li><li>**[!UICONTROL 開始]**：您可在當日、當週、當月、當季、今年之間做選擇。</li><li>**[!UICONTROL 結束]**：您可在當日、當週、當月、當季、今年之間做選擇。</li></ul><br>預設為已選取。 |

1. 請選取「[!UICONTROL **儲存**]」。

## 範例：「兩個月前」的日期範圍 {#section_C4109C57CB444BB2A79CC8082BD67294}

下列自訂日期範圍會顯示「兩個月前」的日期範圍，而「摘要變更」視覺效果會顯示方向變化。

![](assets/date-range-two-months-ago.png)

自訂日期範圍會顯示在您專案中的「[!UICONTROL 日期範圍]」元件面板上方：

![](assets/date-range-panel-two-months-ago.png)

您可將此自訂日期範圍拖曳至使用「上個月」預設集之自訂每月滾動日期範圍旁的欄中，用以進行比較。新增「摘要變更」視覺效果並選取每個欄的總計，顯示方向變化：

![](assets/date-range-two-months-table.png)

## 範例：使用 7 天滾動日期範圍 {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

您可以建立一個日期範圍，指定在一週前結束的 7 天滾動期間：

![](assets/create_date_range.png)

使用&#x200B;*`rolling daily`*。

* 開始設定是 *`current day minus 6 days`*。

* 結束設定是 *`current day minus 7 days`*。

您可將此日期範圍當做元件，拖曳至其他自由表格上。
