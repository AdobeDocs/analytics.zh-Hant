---
description: 學習在 Workspace 專案中工作的基礎知識。
keywords: Analysis Workspace
title: 專案概觀
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: c368ff6c4ac1636a4d1d910b9f1738ff8208fe0a
workflow-type: tm+mt
source-wordcount: '1554'
ht-degree: 50%

---

# 專案概觀

Workspace 專案可讓您合併資料元件、表格和視覺效果，以進行分析並與貴組織的任何人分享。在開始第一個專案之前，請先了解如何存取、瀏覽及管理您的專案。

以下是有關如何建立工作區專案的影片：


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckout](/help/assets/icons/VideoCheckedOut.svg) [建置Workspace專案](https://video.tv.adobe.com/v/334076?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


## 專案清單 {#project-list}

當您初次前往 **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** 時，此頁面會列出您擁有或他人與您共用的所有專案。此頁面也是Adobe Analytics的登陸頁面，除非您先前已設定自訂登陸頁面。

「專案」頁面包含下列資訊：

| 元素 | 說明 |
|---|---|
| [編輯偏好設定](/help/analyze/analysis-workspace/user-preferences.md) | 管理您建立的所有新專案或面板的Analysis Workspace設定及其相關元件。 |
| [建立資料夾](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | 將新的資料夾或子資料夾新增至專案和資料夾清單。 |
| [建立專案](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md) | 從頭開始或從報表開始新專案。 |
| 顯示更多 | 這個選取範圍顯示建立空白專案或行動計分卡的選項、[檢視訓練教學課程](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction)或[檢視發行說明](/help/release-notes/latest.md)。 |
| ![顯示篩選器](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) | 顯示或隱藏篩選器。 您可以按標籤、報表套裝、所有者、型別（專案、資料夾、行動計分卡）和其他篩選器來篩選。 |
| ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) | 使用搜尋欄位來搜尋資料夾、Workspace專案或行動計分卡。 |
| 顯示資料夾和專案 | 選擇是否要顯示專案的資料夾結構。 如需詳細資訊，請參閱[關於 Analytics 資料夾](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)。 |
| ![自訂資料表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) | 此圖示可讓您自訂專案清單中每個專案所顯示的欄。 |

專案清單可顯示下列欄：

| 欄 | 說明 |
|---|---|
| [!UICONTROL 名稱] | Workspace專案名稱。 選取![資訊](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)以顯示包含專案或資料夾詳細資訊的快顯視窗。 選取![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)以顯示可用的動作。 如需詳細資訊，請參閱[管理專案](#manage-projects)。 |
| [!UICONTROL 類型] | 指出此專案是Workspace專案、資料夾還是[行動計分卡](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/mobapp/home)。 |
| [!UICONTROL 標記] | 已套用到專案中的標籤。 |
| [!UICONTROL 已排程] | 表示專案是否已排程以電子郵件傳送給收件者。 請參閱[排程專案](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md)。 |
| 共用連結 (任何人) | 您可與任何人共用專案，即使對方無權存取Analysis Workspace。 此欄顯示是否已以這種方式共用專案。 如需更多資訊，請參閱[共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md)中的「[與任何人共用專案 (無需登入)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link)」。 |
| [專案角色](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/curate-share/share-projects) | 指示您在專案中的角色 - 所有者、編輯、複製、檢視。 |
| [!UICONTROL 報告套裝] | 與專案相關聯的報表套裝。 |
| [!UICONTROL 所有者] | 建立此專案的人 (您或與您共用專案的人)。 |
| [!UICONTROL 共用對象] | 已與其共用該專案的使用者。 |
| [!UICONTROL 上次修改日期] | 上次修改專案的日期和時間。 |
| [!UICONTROL 上次開啟] | 上次開啟專案的日期和時間。 |
| [!UICONTROL 上次使用] | 專案上次使用的日期與時間。 |
| [!UICONTROL 專案 ID] | 專案 ID。 |
| [!UICONTROL 最大日期範圍] | 專案的最長日期範圍。 |
| [!UICONTROL 查詢數] | 專案中使用的查詢總數。 |
| [!UICONTROL 位置] | 專案所在的資料夾。 |

### 管理專案

若要管理專案，請從專案清單中選取一或多個專案。

從藍色動作列中，您可以選取下列動作：

| 動作 | 說明 |
|---|---|
| ![刪除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg)刪除 | 選取後，確認對話方塊會提示您確認刪除Workspace專案或行動計分卡。 選取「**[!UICONTROL 確定]**」以確認。 |
| ![共用](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)共用 | 此動作可讓您共用專案。 請參閱[共用專案](../curate-share/share-projects.md)。 |
| ![重新命名](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)重新命名 | 開啟&#x200B;**[!UICONTROL 重新命名： *名稱&#x200B;*]**&#x200B;對話方塊以重新命名專案。 選取&#x200B;**[!UICONTROL 儲存&#x200B;]**&#x200B;以儲存專案的新名稱。 |
| ![副本](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg)副本 | 立即將選取的專案複製到名稱為&#x200B;*原始名稱*&#x200B;的新專案（複製）。 |
| ![釘選](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg)釘選 | 立即將專案釘選到清單頂端。 新增![Pin](https://spectrum.adobe.com/static/icons/workflow_18/Smock_PinOff_18_N.svg)指標。 |
| ![標籤](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Label_18_N.svg)標籤 | 開啟&#x200B;**[!UICONTROL 標籤專案]**&#x200B;對話方塊。 您可以選取現有標籤或新增標籤。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存專案的標籤。 |
| ![（取消）核准](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CheckmarkCircle_18_N.svg)核准或取消核准 | 核准或取消核准專案。 |
| ![匯出CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg)匯出CSV | 立即下載包含逗號分隔專案值清單的檔案。 |
| ![移至](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FolderAddTo_18_N.svg)移至 | 此動作可讓您將專案移動到資料夾。 在&#x200B;**[!UICONTROL 選取資料夾]**&#x200B;對話方塊中，從&#x200B;**[!UICONTROL 資料夾]**&#x200B;清單中選取資料夾，然後選取&#x200B;**[!UICONTROL 移動]**。 |


## 功能表列 {#menu-bar}

在專案中，功能表會提供管理專案、新增元件、尋找說明等功能的選項。您也可以使用鍵盤[捷徑](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys)來存取每個功能表選項。


| 功能表項目 | 說明 |
|---|---|
| 專案 | 此選單包含專案管理的常見動作，包括新增、開啟、儲存、另存新檔和[另存為公司報告](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md)。 您也可以按一下「重新整理專案」來重新整理整個專案，以擷取最新資料和定義。「[下載 CSV 和 PDF](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/curate-share/download-send)」選項可讓您從 Workspace 匯出資料。「[專案資訊和設定](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview)」提供管理專案的多個選項。 |
| 編輯 | 還原或重做您的上一個操作。「全部清除」會將您的專案重設為空白起點。 |
| 插入 | 從此功能表插入新面板或視覺效果。您也可以從左側欄插入新面板和視覺效果。 |
| [元件](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components) | 從您的專案建立新區段、計算量度、日期範圍或警報元件。您也可以從左側欄建立新元件。如果您的元件定義最近已變更，「重新整理元件」會擷取最新定義。 |
| [Share](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/curate-share/send-schedule-files) | 組織、共用及排程 PDF/CSV 專案給貴組織中的收件者。 |
| 說明 | 存取線上文件、影片及 Analytics [Experience League 社群](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)。管理 Workspace 秘訣及[偵錯工具](https://developer.adobe.com/analytics-apis/docs/2.0/)的可見度。尋找有關 Workspace 及影響專案[效能](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/workspace-faq/optimizing-performance)之因素的詳細資訊。 |
| 「共用」按鈕或所有者 | 如果您是專案的所有者或編輯者，右上方的「共用」按鈕為您提供管理專案收件者的單鍵存取權。如果您擁有專案的複製或檢視角色，您會看到專案所有者的名稱。 |

### 專案資訊和設定 {#info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="計算重複實例數"
>abstract="指定是否要將重複實例計入報表中。<br/><br/>注意，此設定不適用於「流程」或「流失」視覺效果。"

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="計算重複實例數"
>abstract="指定是否要將重複實例計入報表中。<br/>注意，此設定不適用於「流程」或「流失」視覺效果。"


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="允許評論"
>abstract="啟用後，Analysis Workspace 中專案的右側邊欄會顯示一個評論區域。"



**[!UICONTROL Workspace]** > **[!UICONTROL 專案]** > **[!UICONTROL 專案資訊與設定]**&#x200B;提供目前作用中專案的專案層級資訊。

![專案資訊](assets/projectinfo.png)

設定包括：

| 設定 | 說明 |
|---|---|
| 專案名稱 | 提供給專案的名稱。按兩下名稱即可進行編輯。 |
| 所有者 | 專案所有者名稱 |
| 上次修改時間 | 上次修改專案的日期。 |
| 標記 | 列出為了方便分類而套用至專案的所有標籤。 |
| 說明 | 說明可用於釐清專案的用途。按兩下說明即可進行編輯。 |
| 計算重複實例數 | 指定是否要將重複例項計入報告。例如，此設定 (啟動時) 會將多個連續頁面檢視視為同一個頁面的多次頁面檢視。 若關閉，則會計為單頁檢視（此設定只會影響特定量度，例如單頁造訪次數）。 **注意**，此設定不適用於「流量」或「流失」視覺效果。 |
| [顯示註解](/help/analyze/analysis-workspace/components/annotations/overview.md) | 指定是否在專案中顯示註解。 |
| [專案調色盤](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes) | 您可以變更用於 Workspace 的分類調色盤，其方式為選擇已針對色盲人士最佳化的立即可用調色盤或指定您的自訂調色盤。此功能會影響工作區中的許多項目，包括大部分的視覺效果。 |
| [檢視密度](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) | 可減少左側欄、自由格式表格和同類群組表格的垂直邊框間距，讓您在畫面上看到更多資料。 |

## 左側欄 {#left-rail}

在專案中，左側欄中有各種圖示可用，每個圖示都代表建置專案的重要工具：

| 圖示 | 功能 |
|---|---|
| ![個面板圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_WebPage_18_N.svg) | [面板](/help/analyze/analysis-workspace/c-panels/panels.md) |
| ![視覺效果圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_GraphBarVertical_18_N.svg) | [視覺化呈現](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) |
| ![元件圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) | [元件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) |
| ![資料字典圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Bookmark_18_N.svg) | [資料字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) |
| ![目錄圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ViewList_18_N.svg) | [目錄](/help/analyze/analysis-workspace/build-workspace-project/project-table-of-contents.md) |

左側欄的元件（維度、量度、區段、日期範圍）與作用中面板資料檢視有關。 藍色邊框會識別作用中面板，而作用中報表套裝會列在元件邊欄的最上方。


## 按右鍵選單

以下是有關在 Analysis Workspace 中使用按右鍵選單的影片：


>[!BEGINSHADEBOX]

檢視![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [使用內容功能表](https://video.tv.adobe.com/v/23981?quality=12&learn=on){target="_blank"}以取得示範影片。

>[!ENDSHADEBOX]

## 專案畫布 {#canvas}

專案畫布是您整合面板、表格、視覺效果和元件以建立分析的地方。專案可以包含許多面板，每個面板都可以有許多表格和視覺效果。

當您想要根據時段、報表套裝或分析使用案例來組織專案時，面板會很有幫助。作用中面板的周圍有彩色邊框，而且可決定左側邊欄中有哪些元件可用。

根據您為專案選擇的起點，您一開始可以在畫布中使用[自由格式表格](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table)或[空白面板](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/panels/blank-panel)。 開始分析的最快速方法是選取一個或多個元件，然後將其拖放到專案畫布上。系統會自動為您呈現資料表格。 [深入瞭解](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/freeform-table)建立資料表的不同選項，或利用可用的[訓練教學課程](https://experienceleague.adobe.com/zh-hant/docs/analytics/analyze/analysis-workspace/home)取得建立第一個專案的更多指導。

![](assets/canvas.png)
