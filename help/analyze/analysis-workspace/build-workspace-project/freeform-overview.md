---
description: 學習在 Workspace 專案中工作的基礎知識。
keywords: Analysis Workspace
title: 專案概觀
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: 602f837689186f232c4c0f8baebbcf911446bc99
workflow-type: tm+mt
source-wordcount: '1539'
ht-degree: 80%

---

# 專案概觀

Workspace 專案可讓您合併資料元件、表格和視覺效果，以進行分析並與貴組織的任何人分享。在開始第一個專案之前，請先了解如何存取、瀏覽及管理您的專案。

以下是有關如何建立工作區專案的影片：

>[!VIDEO](https://video.tv.adobe.com/v/334076/?quality=12)

## 專案清單 {#project-list}

當您初次前往 **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** 時，此頁面會列出您擁有或他人與您共用的所有專案。這也是 Adobe Analytics 的登陸頁面，除非您之前已設定自訂登陸頁面。

![](assets/sample-project.png)

「項目」頁包含以下資訊：

>[!NOTE]
>
>預設情況下不顯示某些列。 要自定義您看到的列，請按一下 **自定義表** 表徵圖 ![自定義表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)。


| 元素 | 說明 |
|---|---|
| [編輯偏好設定](/help/analyze/analysis-workspace/user-preferences.md) | 管理您建立的所有新項目或面板的Analysis Workspace及其相關元件的設定。 |
| [建立資料夾](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | 將新資料夾或子資料夾添加到項目和資料夾清單中。 |
| [建立專案](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) | 從頭開始或從報表開始新項目。 |
| 顯示更多 | 顯示建立空白項目或移動記分卡的選項， [查看培訓教程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html?lang=zh-Hant)或 [查看發行說明](/help/release-notes/latest.md)。 |
| 顯示資料夾和項目 | 選擇是否顯示項目的資料夾結構。 如需詳細資訊，請參閱[關於 Analytics 資料夾](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)。 |
| 自定義表（表徵圖） | 允許您自定義「項目」頁上每個項目顯示的資訊。 |
| 名稱 | Workspace 專案名稱。 |
| 類型 | 指示這是Workspace項目、資料夾還是 [移動記分卡](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html?lang=zh-Hant)。 |
| 標記 | 已套用到專案中的標籤。 |
| 已排程 | 指示是否計畫按計畫通過電子郵件將項目發送給收件人。 請參閱 [計畫項目](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md)。 |
| 共用連結 (任何人) | 項目可以與任何人共用 — 即使是無法訪問Analysis Workspace的人。 此列顯示項目是否已以此方式共用。 請參閱 [與任何人共用項目（無需登錄）](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link) 在 [共用項目](/help/analyze/analysis-workspace/curate-share/share-projects.md) 的子菜單。 |
| 報表套裝 | 項目關聯的報表套件。 |
| [專案角色](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hant) | 指示您在專案中的角色 - 所有者、編輯、複製、檢視。 |
| 所有者 | 建立此專案的人 (您或與您共用專案的人)。 |
| 共用對象 | 已與項目共用的用戶。 |
| 上次修改時間 | 上次修改專案的日期和時間。 |
| 上次開啟時間 | 上次開啟項目的日期和時間。 |
| 專案 ID | 項目的ID。 |
| 最大日期範圍 | 項目的最長日期範圍。 |
| 查詢數 | 項目中包含的查詢總數。 |
| 位置 | 項目所在的資料夾。 |

## 功能表列 {#menu-bar}

在專案中，功能表會提供管理專案、新增元件、尋找說明等功能的選項。每個功能表選項也都可以使用鍵盤[快速鍵](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html?lang=zh-Hant)進行存取。

![](assets/menu.png)

| 功能表項目 | 說明 |
|---|---|
| 專案 | 包括項目管理的常用操作，包括「新建」、「開啟」、「保存」、「另存為」和 [另存為公司報表](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)。 您也可以按一下「重新整理專案」來重新整理整個專案，以擷取最新資料和定義。「[下載 CSV 和 PDF](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=zh-Hant)」選項可讓您從 Workspace 匯出資料。「[專案資訊和設定](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview.html?lang=zh-Hant?#info-settings)」提供管理專案的多個選項。 |
| 編輯 | 還原或重做您的上一個操作。「全部清除」會將您的專案重設為空白起點。 |
| 插入 | 從此功能表插入新面板或視覺效果。您也可以從左側欄插入新面板和視覺效果。 |
| [元件](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=zh-Hant) | 從您的專案建立新區段、計算量度、日期範圍或警報元件。您也可以從左側欄建立新元件。如果您的元件定義在最近有了變更，「重新整理元件」將會擷取最新的定義。 |
| [共用](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files.html?lang=zh-Hant) | 監管、共用及排程 PDF/CSV 專案給貴組織中的收件者。 |
| 說明 | 存取線上文件、影片及 Analytics [Experience League 社群](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)。管理 Workspace 秘訣及[偵錯工具](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md)的可見度。尋找有關 Workspace 及影響專案[效能](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance.html?lang=zh-Hant)之因素的詳細資訊。 |
| 「共用」按鈕或所有者 | 如果您是專案的所有者或編輯者，右上方的「共用」按鈕為您提供管理專案收件者的單鍵存取權。如果您擁有專案的複製或檢視角色，您將會看到專案所有者的名稱。 |

### 專案資訊和設定 {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL 專案]** > **[!UICONTROL 專案資訊和設定]** 提供目前使用中專案的專案層級資訊。

![](assets/projectinfo.png)

設定包括：

| 設定 | 說明 |
|---|---|
| 專案名稱 | 提供給專案的名稱。按兩下名稱即可進行編輯。 |
| 建立者 | 專案所有者名稱 |
| 上次修改時間 | 上次修改專案的日期。 |
| 標記 | 列出為了方便分類而套用至專案的所有標籤。 |
| 說明 | 說明可用於釐清專案的用途。按兩下說明即可進行編輯。 |
| 計算專案中的重複例項 | 指定是否要將重複例項計入報表。例如，此設定 (啟動時) 會將多個連續頁面檢視視為同一個頁面的多次頁面檢視。 若關閉，則會計為單頁檢視 (這只會影響特定量度，例如單次頁面造訪次數)。 **注意**，此設定不適用於「流量」或「流失」視覺效果。 |
| [專案調色盤](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html?lang=zh-Hant) | 您可以變更用於 Workspace 的分類調色盤，其方式為選擇已針對色盲人士最佳化的立即可用調色盤或指定您的自訂調色盤。此功能會影響工作區中的許多項目，包括大部分的視覺效果。 |
| [檢視密度](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=zh-Hant) | 可減少左側欄、自由格式表格和同類群組表格的垂直邊框間距，讓您在畫面上看到更多資料。 |

## 左側欄 {#left-rail}

在專案中，可以從左側欄存取[面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=zh-Hant)、表格、[視覺效果](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=zh-Hant)和[元件](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=zh-Hant)。這些都是專案的組成要素。

您也可以從[空白面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=zh-Hant)存取視覺效果和面板。

左側欄的元件 (維度、量度、區段、日期範圍) 與作用中面板報表套裝有關。作用中面板的周圍有藍色邊框，而且作用中報表套裝將會列在元件邊欄的最上方。

![](assets/left-rail.png)

## 按右鍵選單

以下是有關在 Analysis Workspace 中使用按右鍵選單的影片：

>[!VIDEO](https://video.tv.adobe.com/v/23981/?quality=12)

## 專案畫布 {#canvas}

專案畫布是您整合面板、表格、視覺效果和元件以建立分析的地方。專案可以包含許多面板，每個面板都可以有許多表格和視覺效果。

當您想要根據時段、報表套裝或分析使用案例來組織專案時，面板會很有幫助。作用中面板的周圍有藍色邊框，而且可決定左側欄中有哪些元件可用。

根據您為專案選擇的起點，您一開始可以在畫布中使用[自由格式表格](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=zh-Hant)或[空白面板](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=zh-Hant)。開始分析的最快速方法是選取一個或多個元件，然後將其拖放到專案畫布上。系統將會自動為您呈現資料表格。[深入了解](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.html?lang=zh-Hant)建立表格的不同選項，或利用我們的[訓練教學課程](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hant?#training-tutorial)以取得建立您的第一個專案的更多指南。

![](assets/canvas.png)

## Project Manager {#manager}

您可以在「**[!UICONTROL Analytics] > [!UICONTROL 元件] > [!UICONTROL 專案]**」底下管理 Analysis Workspace 專案。 Project Manager 會顯示特定使用者已建立的項目。

您可以在「[!UICONTROL 管理員] > [!UICONTROL Analytics 使用者和資產] > [!UICONTROL 轉移資產]」底下將專案所有權轉移給新使用者。

在 Projects Manager 中，您可以新增、標記、共用、複製及進行更多操作。在搜尋列中搜尋專案，或使用左側欄中的篩選選項進行搜尋。您可以依標籤、所有者、專案類型等條件進行篩選。

![](assets/project-manager.png)

以下是 Projects Manager 中的常見操作，您可以一次針對一個或多個專案進行這些操作：

| 動作 | 說明 |
|---|---|
| 新增 | 從頭建立新項目或從 [報告](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)。 |
| 標記或核准 | 選擇「標籤」或「批准」以組織您的項目並使其更易於搜索。 |
| [共用](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hant) | 將專案提供給貴組織中的其他 Analysis Workspace 用戶使用。 |
| 刪除 | 刪除您的專案。 |
| 重新命名 | 編輯您的專案名稱。 |
| 複製 | 建立專案的重複複本。這會建立新專案和專案 ID。將不會複製與原始專案綁定的任何共用或排程。 |
| 匯出至 CSV | 將專案下載為 CSV 檔案，其中包含純文字資料。 |
