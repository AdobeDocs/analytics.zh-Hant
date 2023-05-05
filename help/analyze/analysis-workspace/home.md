---
title: Analysis Workspace 總覽
description: Analysis Workspace 是 Adobe Analytics 的首要分析工具。它可讓您使用面板、表格、視覺效果和其他元件好讓資料栩栩如生、組織資料集、共用及排程專案，還有其他功能。
feature: Workspace Basics
role: User, Admin
exl-id: de95551d-09ea-4461-9bb4-b4ef235e9cd2
source-git-commit: 33e2ca30ec385861c35c9d06e870d5b38d8f2e34
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 36%

---

# Analysis Workspace 概述

Analysis Workspace可讓您快速建立分析，以收集深入分析，然後與其他人共用這些分析。 您可以使用拖放瀏覽器介面建立分析、新增視覺效果以生動呈現資料、組織資料集，以及與任何您選擇的人共用及排程專案。

以下影片提供簡要概述，其中提供可能的範例。

>[!VIDEO](https://video.tv.adobe.com/v/26266/?quality=12)

## Analysis Workspace地區

下圖及隨附的表格說明了Analysis Workspace的部分主要區域：

![Analysis Workspace 概觀](assets/analysis-workspace-overvew.png)

| 影像中的位置 | 名稱和函式 |
|---------|----------|
| A | **最左側邊欄：** 包含標籤，可將面板、視覺效果和元件新增至Analysis Workspace。 也包含用來開啟資料字典的資料字典圖示。 |
| B | **左側邊欄：** 此區域會根據左側邊欄中選取的標籤，包含個別的面板、視覺效果或元件。 |
| C | **畫布：** 這是從左側邊欄拖動內容以構建項目的主要區域。 您新增面板、視覺效果和元件至畫布時，專案會動態更新。 |
| D | **報表套裝下拉式功能表：** 針對Analysis Workspace中的每個面板，報表套裝下拉式功能表可讓您選擇要作為資料來源的報表套裝。 |

## Analysis Workspace功能 {#analysis}

以下是Analysis Workspace提供的部分主要功能：

### 面板

**面板**&#x200B;可供在專案中組織可能包含許多表格和視覺效果的分析。Analysis Workspace 中提供的許多面板皆可根據用戶輸入的少量內容，產生完整的分析集。在左側邊欄中，選取頂端的&#x200B;**[!UICONTROL 「面板」]**&#x200B;圖示，即可檢視完整的可用面板清單。

若要進一步了解面板，請參閱 [面板概觀](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html).

![](assets/build-panels.png)

### 視覺效果

**視覺效果**，例如長條圖或折線圖，可以透過視覺化方式生動呈現資料。 在左側邊欄中，選取中間的&#x200B;**[!UICONTROL 「視覺效果」]**&#x200B;圖示，即可檢視完整的可用視覺效果清單。

若要進一步了解視覺效果，請參閱 [視覺效果概述](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html).

![](assets/build-visualizations.png)

### 元件

Analysis Workspace中的元件包含下列項目：

* 維度

* 量度

* 區段

* 日期範圍

若要進一步了解這些元件類型，請參閱 [元件概觀](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).

這些元件類型都可新增至視覺效果（例如自由表格），以開始回答您的業務問題。

了解元件術語後，您可以將元件拖曳至視覺效果（包括自由表格）以 [建立分析](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

![](assets/build-components.png)

### 資料字典

Analysis Workspace 中的資料字典可幫助使用者和管理員追蹤並深入了解在其 Analytics 環境中的元件。

若要進一步了解資料字典，請參閱 [資料字典概觀](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

## 開始使用Analysis Workspace

### 登入 Adobe Analytics {#login}

若要開始使用 Analysis Workspace，請前往 [experience.adobe.com/analytics](https://experience.adobe.com/analytics) 登入 Adobe Analytics。預設會顯示Analysis Workspace的「專案」頁面。 如果已為您選取特定專案，該專案預設會顯示。

### 建立 專案 {#new-project}

在Analysis Workspace中的分析稱為 [專案](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

您可以在Analysis Workspace中建立專案，如 [建立專案](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md).

項目可以組織為資料夾和子資料夾，如 [Analysis Workspace中的資料夾](/help/analyze/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### 儲存並共用專案

當您在Analysis Workspace中建立分析時，您的工作是 [自動儲存](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

當您完成建立專案並收集可操作的深入分析時，專案即可供其他人使用。 您可以與組織內的使用者和群組，甚至與組織外的人員共用專案。 如需共用專案的相關資訊，請參閱 [共用專案](/help/analyze/analysis-workspace/curate-share/share-projects.md).

<!--

Maybe add this back in if the video isn't too outdated. Otherwise, delete this section.

### Project management in Analysis Workspace

The following video provides an overview of project management in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/24035/?quality=12)

-->

## 使用虛擬分析人員更了解異常

Virtual Analyst是Adobe Analytics中的一組功能，可運用預測演算法和機器學習來針對影響您業務的異常現象提供深入分析。 它能讓您自動處理最常見也最昂貴的資料科學工作流程，藉此識別造成在您的資料中引起不正常行為的原因。

Virtual Analyst 包含下列功能：

* [異常偵測：](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md)此功能提供的統計方法，可判斷指定量度和先前的資料相比有何變更。
* [貢獻分析：](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/run-contribution-analysis.md)可協助判別對資料造成異常的最大因素。
* [智慧型警報：](/help/analyze/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)主動識別並通知您資料中的異常情況，進而加快洞察原因。

## 其他資源 {#resources}

* Adobe 提供數百項 [Analytics 影片培訓教學課程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/overview.html?lang=zh-Hant)。
* 如需有關新功能的更新，請參閱 [Adobe Experience Cloud 發行說明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html#analytics)。
* 若要熟悉Analysis Workspace，可使用Analysis Workspace培訓教學課程範本。 此範本會逐步引導您了解常用術語，以及在工作區中首次建立分析的步驟。 若要開始進行教學課程：
   1. 在 [!UICONTROL **工作區**] 標籤，選取 **[!UICONTROL 學習]** 左邊。
   1. 選擇 **[!UICONTROL 開啟教學課程]**.
      ![](assets/training-tutorial.png)

