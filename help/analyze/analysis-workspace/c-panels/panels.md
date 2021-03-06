---
description: 面板是表格與視覺效果的集合。
title: 面板概觀
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: bcfcba4093f051e2d4132fb2c45ab66d76ba192d
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 95%

---

# 面板概觀

[!UICONTROL 面板]是表格與視覺效果的集合。您可以從「工作區」左上角圖示或[空白面板](blank-panel.md)來存取面板。當您想要根據時段、報表套裝或分析使用案例來組織專案時，面板會很有幫助。

## 面板類型

Analysis Workspace 中有以下面板類型:

| 面板名稱 | 說明 |
| --- | --- |
| [空白面板](blank-panel.md) | 從可用面板和視覺效果中選擇以開始分析。 |
| [快速深入分析面板](quickinsight.md) | 快速建立自由格式表格和隨附的視覺效果，以更快速分析及揭秘深入分析。 |
| [Analytics for Target 面板](a4t-panel.md) | 在 Analysis Workspace 中分析 Target 的活動和體驗。 |
| [歸因面板](attribution.md) | 使用任何維度和轉換量度，快速比較和視覺化任何數量的歸因模式。 |
| [自由表格面板](freeform-panel.md) | 執行無限制的比較和劃分，然後新增視覺效果以展現一個有豐富資料的故事。 |
| [「媒體平均每分鐘觀眾數」面板](average-minute-audience-panel.md) | 分析一段時間的平均每分鐘觀眾數，包含尖峰觀看次數的詳細資訊，並能夠加以細分及比較。 |
| [媒體同時檢閱者面板](media-concurrent-viewers.md) | 分析不同時段的同時檢閱者，並取得尖峰檢閱情形的詳細資訊，並可加以劃分及比較。 |
| [「媒體播放時間」面板](media-playback-timespent/media-playback-time-spent.md) | 分析不同時段的同時檢閱者，並取得尖峰檢閱情形的詳細資訊，並可加以劃分及比較。 |
| [區段比較面板](c-segment-comparison/segment-comparison.md) | 快速比較所有資料點的兩個區段，以自動找到相關的差異。 |

![](assets/panel-overview.png)

「[!UICONTROL 快速深入分析]」、「[!UICONTROL 空白]」與「[!UICONTROL 自由圖形]」面板適用於開始分析的階段，而 [!UICONTROL Analytics for Target]、「[!UICONTROL Attribution IQ]」、「[!UICONTROL 媒體同時檢閱者]」與「[!UICONTROL 區段比較]」則適用於更進階的分析。專案中也有 `"+"` 按鈕可供使用，讓您隨時都可以新增空白面板。

預設的開始面板為「[!UICONTROL 自由格式]」面板，但您也可以將[空白面板](/help/analyze/analysis-workspace/c-panels/blank-panel.md)設為預設面板。

## 報表套裝 {#report-suite}

面板內的表格和視覺效果是從面板右上角所選[!UICONTROL 報表套裝]衍生而得。該報表套裝也會決定左側邊欄內會有哪些元件。在專案中，您可以使用一或[多個報表套裝](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html)，多寡視您的分析使用情形而定。若要將單一報告套件套用在專案內所有面板，**在面板標題上按一下右鍵 > 套用至所有面板**。

報表套裝清單是依關聯性來分類；Adobe 是根據目前用戶最近使用套裝情形和多常使用套裝，以及組織內多常使用套裝等來定義關聯性。

![](assets/panel-report-suite.png)

## 行事曆 {#calendar}

行事曆面板會儀表板內表格和視覺效果的報告範圍。

>[!NOTE]
>如果表格、視覺效果或面板下拉區域內使用了 (紫色) 日期範圍元件，它會覆蓋面板行事曆。

![](assets/panel-calendar.png)

您可在面板行事曆的進階設定下套用以分鐘為單位的日期範圍。如果您的報表涵蓋許多天的日期範圍，則開始時間會套用在您的範圍中的第一天，而結束時間則會套用在最後一天。

## 下拉區域 {#dropzone}

面板下拉區域可讓您將區段和下拉篩選器套用至面板內的所有表格和視覺效果。 您可以將一個或多個篩選器套用至面板。每個篩選器上方標題都可編輯，方法是按一下編輯鉛筆圖示；或者，按一下右鍵可完全移除篩功能表。

### 區段篩選

將任何區域從左側邊欄拖放至面板下拉區域，即可開始篩選您的面板。

![](assets/segment-filter.png)

### 即席段篩選器

還可以將非段元件直接拖動到放置區域中以建立即席段，從而節省了轉至段生成器的時間和精力。 以此方法建立的區段會自動被定義為點擊層級的區段。若要編輯此定義，可按一下區段旁邊的資訊圖示 (i)，然後按一下筆狀編輯圖示並在，即可在區段產生器內進行編輯。

臨時段是項目的本地段，除非將它們公開，否則不會顯示在左欄中。

![](assets/adhoc-segment-filter.png)

### 下拉篩選器 {#dropdown-filter}

除了區段篩選器外，下拉篩選器還可讓您以可控制方法進行資訊互動。例如，您可新增行動裝置類型的下拉篩選器，因此您就可以將面板區分為平板電腦、手機或桌面電腦等區段。

下拉篩選器也可用來將許多專案整合為一。例如，如果您的一個專案擁有套用不同國家區段的許多版本，您可以將所有版本整合為單一專案並新增一個國家/地區的下拉篩選器。

![](assets/dropdown-filter-intro.png)

若要建立下拉篩選器：

1. 若要使用[!UICONTROL 維度項目] (例如[!UICONTROL 行銷管道]維度內的值) 建立下拉篩功能表，在左側邊欄內您的維度旁邊，按一下向右的箭頭。如此即可使用所有適用項目。在左側邊欄中選取一個或多個元件項目，然後&#x200B;**按住 Shift 鍵**，將元件放至面板的下拉區域中。這樣便可將這些元件轉變為下拉篩選器，而不會成為單一的區段。
1. 若要使用其他元件 (如量度、區段或日期範圍) 建立下拉篩選器，在左側邊欄中選取一個元件類型，然後&#x200B;**按住 Shift 鍵**，將元件放至面板的下拉區域中。
1. 從下拉功能表中選取一個選項，即可變更面板中的資料。您也可選擇不要篩選任何面板中的資料，只要選取「**[!UICONTROL 不要篩選]**」即可。

![](assets/create-dropdown.png)

[觀看影片](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html)，了解更多有關如何在專案中新增下拉篩選器。

## 按右鍵選單 {#right-click}

在面板標題按一下右鍵，可以使用面板的其他功能。

![](assets/right-click-menu.png)

有以下設定可使用：

| 設定 | 說明 |
| --- | --- |
| 插入複製的面板/視覺效果 | 允許您將複製的面板或視覺效果貼至 (「插入」) 專案內另一個位置或完全不同的專案中。 |
| 複製面板 | 允許您按一下右鍵並複製面板，這樣您便可插入專案內另一個位置或完全不同的專案中。 |
| 將報表套裝套用至所有面板 | 允許您將主要面板報表套裝套用至專案中的所有面板。 |
| 複製面板 | 將目前的面板依樣複製，然後再修改資料。 |
| 摺疊/展開所有面板 | 摺疊和展開所有專案面板。 |
| 摺疊/展開面板中的所有視覺效果 | 摺疊和展開目前面板中的所有視覺效果。 |
| 編輯說明 | 新增 (或編輯) 面板的文字說明。 |
| 取得面板連結 | 讓您可將用戶直接導向專案中的特定面板。收件者按一下連結後必須先登入系統，然後才會被導向所連結的正確面板。 |
