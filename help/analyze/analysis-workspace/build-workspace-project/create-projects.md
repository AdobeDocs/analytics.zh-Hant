---
description: 了解如何在 Analysis Workspace 中建立專案。
title: 建立專案
feature: Workspace Basics
role: User, Admin
exl-id: 24193013-1361-43fc-b129-c44f207d9101
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 93%

---

# 建立專案 {#create-projects}


Analysis Workspace 中的[專案](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md)讓您建立和檢視關鍵業務分析。這些分析可以與組織內部或外部的利害關係人共用。

1. 在 Adobe Analytics 中，選取「**[!UICONTROL Workspace]**」。

1. 在左側面板中選取&#x200B;**[!UICONTROL 專案]**，然後選取&#x200B;**[!UICONTROL 建立專案]**。

1. 選取&#x200B;**空白 Workspace 專案**，以使用瀏覽器建立您的 Workspace 專案。

   請參閱[空白行動計分卡](/help/analyze/mobile-app/curator.md)，以取得有關如何建立行動計分卡專案的詳細資訊，而您可使用行動應用程式與其他利害關係人共用。

1. 選取&#x200B;[!UICONTROL **建立**]。


現在您已經建立空白 Workspace 專案，請確保您熟悉 [Analysis Workspace](/help/analyze/analysis-workspace/home.md) 使用者介面。確認後，即可建置您的專案。若要進行此步驟：

![Example project](assets/example-project.png)

* 新增[面板](/help/analyze/analysis-workspace/c-panels/panels.md)至您的專案。例如，**[!DNL Example Panel]** ➊。

* 新增[視覺化呈現](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md)至您的面板。例如：
   * **[!DNL Line]** [折線圖](/help/analyze/analysis-workspace/visualizations/line.md)視覺內容➋
   * **[!DNL US States]** [自由格式表格](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)視覺內容➌
* 新增[元件](/help/analyze/analysis-workspace/components/analysis-workspace-components.md)至您的視覺效果。例如：
   * **[!DNL US States]** [維度](/help/components/dimensions/overview.md) ➍
   * **[!DNL Unique Visitors]** [量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md) ➎
   * **[!DNL Average Revenue Per Order]** [計算量度](/help/components/calculated-metrics/cm-overview.md) ➏
   * **[!DNL Visits from Mobile Devices]** [區段](/help/components/segmentation/seg-overview.md) ➐
   * **[!DNL Last Month]** [日期範圍](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md) ➑
   * **[!DNL Example]** [註解](/help/analyze/analysis-workspace/components/annotations/overview.md) ➒


## 專案資訊和設定 {#project-info-settings}

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


專案資訊和設定可提供目前使用中專案的專案層級資訊。

![The Project Info &amp; Settings window.](./assets/projectinfo.png)

設定包括：

| 設定 | 說明 |
|---|---|
| 專案名稱 | 提供給專案的名稱。按兩下名稱即可進行編輯。 |
| 所有者 | 專案所有者名稱 |
| 修改時間 | 上次修改專案的日期。 |
| 標記 | 列出為了方便分類而套用至專案的所有標籤。 |
| 說明 | 說明可用於釐清專案的用途。按兩下說明即可進行編輯。 |
| 計算重複實例數 | 指定是否要將重複實例計入報告中。注意，此設定不適用於「流程」或「流失」視覺化呈現。 |
| 顯示註解 | 指定是否顯示此專案的註解。 |
| [專案調色盤](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md) | 您可以變更用於 Workspace 的分類調色盤，其方式為選擇已針對色盲人士最佳化的立即可用調色盤或指定您的自訂調色盤。此功能會影響工作區中的許多項目，包括大部分的視覺效果。 |
| [檢視密度](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) | 可減少左側面板、自由格式表格和同類群組表格的垂直邊框間距，讓您在畫面上查看更多資料。 |



<!--
# Create projects in Analysis Workspace

[Projects](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace allow you to view business-critical analyses that can be shared with stakeholders inside or outside your organization. 

For general information about how to get started using Analysis Workspace, see [Analysis Workspace overview](/help/analyze/analysis-workspace/home.md).

The following sections describe how to create a project and start adding the key building blocks for any Analysis Workspace project: panels, visualizations, and components.

## Create a project from a blank project or a report

1. In Adobe Analytics, select [!UICONTROL **Workspace**].

1. Choose whether to create a blank project or to create a project from a report:

   +++Create a blank project

   1. On the [!UICONTROL **Workspace**] tab, select the [!UICONTROL **Projects**] tab on the left side of the page, then select [!UICONTROL **Create project**].

   1. Choose whether to create a blank project or a blank mobile scorecard

      * **Blank project** if you plan to share your analysis from the browser 
      * [**Blank mobile scorecard**](/help/analyze/mobile-app/curator.md) if you plan to share your analysis from the Adobe Analytics dashboards mobile app.

   1. Select [!UICONTROL **Create**].

   +++

   +++Create a project from a report
   
      1. On the [!UICONTROL **Workspace**] tab, select the [!UICONTROL **Reports**] tab on the left side of the page.

      1. Search for or navigate to the report you want to use, then select it when it appears.

          A set of standard reports is available by default. In addition, your organization might have created custom reports for you to choose from.
          
      1. Select [!UICONTROL **Project**] > [!UICONTROL **Save**] to save the report as a new project.

          For more information about reports, see "Navigate the Reports tab" in [Adobe Analytics landing page](/help/analyze/landing.md).

   +++

1. Next, you need to add panels, visualizations, and components to your project. First, add panels to your project in Analysis Workspace, as described in [Add panels to the project](#add-panels-to-the-project). You can then add visualizations to any panels. Finally, you can add components to any panels or visualizations.

## Add panels to the project {#panels}

[Panels](/help/analyze/analysis-workspace/c-panels/panels.md) are the foundation to any project in Analysis Workspace. Panels are used to organize the content (visualizations and components) of a project. 

Many of the panels provided in Analysis Workspace generate a full set of analyses based on a few user inputs. 

To add a panel:

1. Select the [!UICONTROL **Panels**] icon in the left rail.

   ![](assets/build-panels.png)

1. Search for the panel you want to add. When it appears in the left rail, drag it into your project.

1. Add visualizations to your panel, as described in [Add visualizations to the project](#add-visualizations-to-the-project). 

   Alternatively, you can add components directly to a panel, as described in [Add components to the project](#add-components-to-the-project).

## Add visualizations to the project

[Visualizations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) (such as a freeform table, a bar chart, or a line chart) can be used to visually bring data to life. 

>[!TIP]
>
>Freeform tables are the most common type of visualization, and are the foundation for interactive data analysis. For more details about how to work with Freeform tables in Analysis Workspace, see [Freeform table](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md).

To add a visualization:

1. Select the **[!UICONTROL Visualizations]** icon in the left rail.

   ![](assets/build-visualizations.png)

1. Search for the visualization you want to add. When it appears in the left rail, drag it to a panel within your project. 

1. Add components to the visualization, as described in [Add components to the project](#add-components-to-the-project).

## Add components to the project

[Components](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) make up the actual data of any project. You can add components to visualizations or to panels.

>[!TIP]
>
>For information about each component, select the Info icon next to a component's name in the left rail, or see the [Analytics Components Guide](/help/components/home.md).

Following is basic information about how to add a component to a project in Analysis Workspace. For more detailed information about adding the various types of components (dimensions, metrics, segments, and date ranges), see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

To add a component to a project in Analysis Workspace:

1. Select the **[!UICONTROL Components]** icon in the left rail.

   ![](assets/build-components.png)

1. Scroll to or search for the component you want to add, then drag it to a panel or visualization within your project. 

   For example, you can drag a segment to the segment drop zone in a panel header.

   ![drop a segment in the drop zone](assets/segment-dropzone.png)

   For more information about adding components to projects, see [Use components in Analysis Workspace](/help/analyze/analysis-workspace/components/use-components-in-workspace.md).

1. (Optional) Share the project as described in [Save and share the project](#save-and-share-the-project).

## Save and share the project

As you create an analysis in Analysis Workspace, your work is [automatically saved](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md). 

When you finish building out the project and it's gathering actionable insights, the project is ready to be consumed by others. You can share the project with users and groups in your organization, or even with people outside your organization. For information about sharing a project, see [Share projects](/help/analyze/analysis-workspace/curate-share/share-projects.md).
-->