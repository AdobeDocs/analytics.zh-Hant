---
source-git-commit: 33ac467cd73e3099ce0ca03aa41cbd4192eb2384
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 96%

---
# 程式碼片段

## Reports &amp; Analytics 生命週期結束通知 {#ra-eol}

>[!IMPORTANT]
>
>自&#x200B;**2024年1月17日起**，Adobe已停止支援Reports &amp; Analytics及其隨附的報告和功能。 Reports &amp; Analytics及其所有報表和排程目前均已停止運作。 支援 Reports &amp; Analytics 的報告、視覺效果和基礎技術不再符合 Adobe 的技術標準。大部分的 Reports &amp; Analytics 功能都可在 Analysis Workspace 中使用。如需有關在Analysis Workspace中使用報表的資訊，請參閱[使用預先建立的報告](/help/analyze/analysis-workspace/reports/use-reports.md)。
> 
>自 Analysis Workspace 在 2015 年發佈以來，Reports &amp; Analytics 功能已移至 Analysis Workspace 並已達到工作流程同位臨界值。本通知說明生命週期結束程序。
>
>進一步了解 Reports &amp; Analytics [生命週期結束公告](https://www.adobe.com/go/analytics_rnaeol_tw)。

## 資料字典篩選條件 {#dd-filter-criteria}

1. (可選) 選取 **篩選器** 圖示 ![資料字典篩選器圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，然後選擇以下任一篩選器選項以篩選元件清單：

| 選項 | 函數 |
|---------|----------|
| [!UICONTROL **已核准**] | 僅顯示標記為由管理員核准的元件。 |
| [!UICONTROL **我的最愛**] | 僅顯示「我的最愛」清單中的元件。有關將元件新增到「我的最愛」清單的資訊，請參閱[元件概觀](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)。 |
| [!UICONTROL **維度**] | 僅顯示維度的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
| [!UICONTROL **量度**] | 僅顯示量度的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
| [!UICONTROL **區段**] | 僅顯示區段的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) <!--this is Filters in Customer Journey Analytics--> |
| [!UICONTROL **日期範圍**] | 僅顯示日期範圍的元件。(當您首次存取資料字典時，此選項也可以在 [!UICONTROL **Quick filters**] 標籤中使用。) |
| [!UICONTROL **全部顯示**] | 顯示所有元件。此選項僅提供給管理員使用。 |
| [!UICONTROL **未經核准**] | 僅顯示尚未由管理員標記為「已核准」的元件。作為管理員，這有助於確定需要您檢閱和核准的元件。此選項僅提供給管理員使用。 |
| [!UICONTROL **缺少說明**] | 僅顯示在說明欄位中還沒有說明的元件。此選項僅提供給管理員使用。 |
| [!UICONTROL **顯示重複項目**] | <p>僅顯示與所選報告套裝中的另一個元件具有相同名稱或相同定義的元件。名稱或定義必須完全相符才能顯示為重複項目。</p><p>此選項僅提供給管理員使用。</p><p>**注意：**&#x200B;對於定義，包括您建立的元件和 Adobe 提供的元件。對於名稱，目前僅包括您建立的元件，不包括 Adobe 提供的元件。顯示 Adobe 提供元件的重複名稱會在未來版本中新增。</p> |
| [!UICONTROL **無最近的資料**] | 僅顯示在過去 90 天內未收集任何資料的元件。此選項僅提供給管理員使用。 |
| [!UICONTROL **由Adobe建立**] <!-- I don't see this option--> | 僅顯示由 Adobe 建立的元件。並不會顯示由管理員或您組織中的其他使用者建立的元件。 |

{style="table-layout:auto"}

## 資料字典元件資訊 {#dd-component-information}

| 選項 | 函數 |
|---------|----------|
| [!UICONTROL **已核准**] | <p>指出該元件已經過管理員檢閱與核准。</p><p>元件獲得核准後，管理員可以選取&#x200B;**已核准**&#x200B;按鈕來取消核准。</p> |
| [!UICONTROL **需要核准**] | <p>指出該元件尚未經過管理員檢閱與核准。</p><p>管理員會看到&#x200B;[!UICONTROL **核准**]&#x200B;的選項。選擇此選項會讓使用者看到元件標記為「已核准」。</p> |
| [!UICONTROL **說明**] | 描述元件的預定功能。(此資訊由 Analytics 管理員新增，如[新增元件說明](/help/analyze/analysis-workspace/components/add-component-descriptions.md)中所述。) |
| [!UICONTROL **經常與下列項目搭配使用**] | <p>顯示您正在查看的元件最常與哪些元件一起使用。</p><p>在 5 種主要元件類型中最多顯示 5 個元件：量度、計算量度、維度、區段和日期範圍。</p><p>此清單顯示過去 90 天的資料。只會顯示您有權檢視的元件。</p><p>管理員可以在「[!UICONTROL **永遠包含**]」和「[!UICONTROL **永遠排除**]」下拉式欄位中選取所需的元件，來管理使用者在此區段中看到的元件。在管理顯示給使用者的元件之前，請先套用&#x200B;**全部顯示**&#x200B;篩選器，以確保您能看到所有未與您共用的元件。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **類似於**] | <p>顯示與您正在查看的元件具有相似名稱的元件。</p><p>在 5 種主要元件類型中最多顯示 5 個元件：量度、計算量度、維度、區段和日期範圍。</p><p>只會顯示您有存取檢視權限的元件。</p><p>報告套裝中的任何重複元件也會顯示在此處。Analytics 管理員應識別並移除所有重複的元件，如[監視資料字典健康情況](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md)中所述。</p><p>管理員可以在「[!UICONTROL **永遠包含**]」和「[!UICONTROL **永遠排除**]」下拉式欄位中選取所需的元件，來管理使用者在此區段中看到的元件。在管理顯示給使用者的元件之前，請先套用&#x200B;**全部顯示**&#x200B;篩選器，以確保您能看到所有未與您共用的元件。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**注意：**&#x200B;目前，「**類似於**」區段僅包括您建立的元件，不包括 Adobe 提供的元件。Adobe 提供的元件會在未來版本中新增。</p> |
| [!UICONTROL **標記**] | 顯示套用於元件的所有標記。具有管理員存取權限的使用者可以在編輯元件時新增標記。 |
| [!UICONTROL **元件類型**] | 列出元件的類型，無論是維度、指標、區段還是日期範圍。 |
| [!UICONTROL **建立者**] | 顯示建立元件的使用者名稱。 |
| [!UICONTROL **預覽**] | 顯示元件在 Analysis Workspace 中的外觀預覽。 |
| [!UICONTROL **上次修改日期**] | 顯示上次修改元件的日期。此部分會在檢視區段、計算量度和日期範圍時顯示。 |

{style="table-layout:auto"}

## 元件排序選項 {#components-sort-options}

| 選項 | 功能 |
|---------|----------|
| [!UICONTROL **建議**] | 以建議置於清單頂端的元件來對元件進行排序。您或貴組織中其他人近期最頻繁使用的元件會顯示在清單的較高位置。 |
| [!UICONTROL **字母順序**] | 依字母順序對元件進行排序。 |
| [!UICONTROL **分類**] | 根據元件類型 (維度、量度、區段、日期範圍) 對元件進行排序。 |

{style="table-layout:auto"}

## 發佈階段有限測試 {#release-limited-testing}

>[!AVAILABILITY]
>
>本文中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能開放使用時，便會刪除此備註。有關 Analytics 發佈流程的資訊，請參閱 [Adobe Analytics 功能發佈](/help/release-notes/releases.md)。

## 發佈階段有限測試部份 {#release-limited-testing-section}

>[!AVAILABILITY]
>
>本區段中描述的功能處於發佈的有限測試階段，可能尚未開放使用於您的環境中。此功能開放使用時，便會刪除此備註。有關 Analytics 發佈流程的資訊，請參閱 [Adobe Analytics 功能發佈](/help/release-notes/releases.md)。


## 外掛程式免責聲明 {#plug-in}

>[!IMPORTANT]
>
>此外掛程式由 Adobe Consulting 提供，協助您從 Adobe Analytics 中獲得更多價值。Adobe 客戶服務不提供此外掛程式的支援，包括安裝或疑難排解在內。如果您需要與此外掛程式有關的協助，請聯絡貴組織的 Adobe 客戶團隊。他們可幫您安排顧問會議，以尋求協助。

