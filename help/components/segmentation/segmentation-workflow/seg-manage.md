---
description: 「區段管理員」提供許多管理區段的方式，例如共用、篩選、標記、核准、複製、刪除和標示為我的最愛。
title: 管理區段（區段管理員）
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: 5819026bd3798cd936094f138cd236b1cb4b278e
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 67%

---

# 管理區段


您可以[共用](t-seg-share.md)、[劃分](t-seg-filter.md)、[標記](seg-tag.md)、[核准](seg-approve.md)、重新命名、[複製](seg-copy.md)、刪除、匯出區段以及將區段標示為[我的最愛](t-seg-favorite.md) (從統一的[!UICONTROL 區段]管理介面進行)。若要管理區段：

* 在主介面中選取「**[!UICONTROL 元件]**」，然後選取「**[!UICONTROL 區段]**」。


>[!NOTE]
>
>您在特定Workspace專案中建立的快速區段不會出現在[!UICONTROL 區段]管理員中，除非您讓該區段可用於您的所有專案。
>

## 區段管理員

區段管理員有以下介面元素：

![區段介面](assets/segments-manager.png)

### 區段清單

區段清單➊會顯示您擁有的所有區段、已設定您所有專案範圍的區段，以及已與您共用的區段。 清單有以下欄位：

| 欄 | 說明 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 選取以將區段設為我的最愛 ![Star](/help/assets/icons/Star.svg) 或取消我的最愛 ![StarOutline](/help/assets/icons/StarOutline.svg)。請參閱[將區段標示為我的最愛](t-seg-favorite.md) |
| **[!UICONTROL 標題和說明]** | 若要編輯區段，請選取標題連結，以開啟[區段產生器](seg-build.md)。 共用的區段會以![共用](/help/assets/icons/ShareAlt.svg)表示。 |
| **[!UICONTROL 報表套裝]** | 套用此區段的報表套裝。 |
| **[!UICONTROL 所有者]** | 區段的所有者。做為使用者，您只能看到您擁有的區段或與您共用的註解。 |
| **[!UICONTROL 標記]** | 此區段的標記。 |
| **[!UICONTROL 共用對象]** | 您將區段與之共用的人數或群組數。選取開啟「**[!UICONTROL 共用元件]**」對話框。如需詳細資訊，請參閱[共用區段](t-seg-share.md)。 |
| **[!UICONTROL 已發佈]** | [區段是否已發佈](seg-publish.md)至Experience Cloud。 |
| **[!UICONTROL 修改日期]** | 上次修改區段的日期和時間。 |

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要顯示的欄位。

### 動作列

您可以使用動作列➋對區段進行動作。 動作列包含以下動作：

| 動作 | 說明 |
|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新增]** | 使用[區段產生器](seg-build.md)新增另一個區段。 |
| ![Search](/help/assets/icons/Search.svg) [!UICONTROL *根據標題搜尋*] | 當未選取清單中任何區段時，請使用此搜尋欄位搜尋區段。 |
| ![Label](/help/assets/icons/Label.svg) **[!UICONTROL 標記]** | 標記所選取之區段。在&#x200B;**[!UICONTROL 標記區段]**&#x200B;對話框中，選取或取消選取所選取之區段的標記。選取「**[!UICONTROL 儲存]**」，儲存所選取之區段的標記。如需詳細資訊，請參閱[標記區段](seg-tag.md)。 |
| ![Share](/help/assets/icons/ShareAlt.svg) **[!UICONTROL 共用]** | 共用所選取之區段。在&#x200B;**[!UICONTROL 共用區段]**&#x200B;對話框中，您可以 ![Search](/help/assets/icons/Search.svg) *搜尋個人或群組*，或者您可以選取「**[!UICONTROL 組織]**」或「**[!UICONTROL 群組]**」。選取「**[!UICONTROL 儲存]**」，儲存所選取之區段的共用詳細資訊。如需詳細資訊，請參閱[共用區段](t-seg-share.md)。 |
| ![Delete](/help/assets/icons/Delete.svg) **[!UICONTROL 刪除]** | 刪除所選取之區段。系統會提示您進行確認。 |
| ![編輯](/help/assets/icons/Edit.svg) **[!UICONTROL 重新命名]** | 重新命名所選取之單一區段。選取後，您可以重新命名內嵌區段。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 核准]** | 核准所選取之區段。如需詳細資訊，請參閱[核准區段](seg-approve.md)。 |
| ![Copy](/help/assets/icons/Copy.svg)  **[!UICONTROL 複製]** | 複製所選取之區段。使用相同的名稱和字尾建立新區段`(Copy)`。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL 匯出為 CSV]** | 將區段匯出為 `Segments List.csv` 檔案。 |

### 使用中的篩選欄

篩選列➌顯示從篩選面板套用至區段清單（如果有的話）的作用中區段。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速移除篩選條件。如果指定了多個篩選器，您可以使用&#x200B;**[!UICONTROL 全部移除]**&#x200B;來移除所有篩選器。

### 篩選面板

您可以使用![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 篩選器]**&#x200B;左側面板➍來篩選區段清單。 篩選器面板會顯示篩選器的型別以及遵循特定篩選器的區段數。 選取![篩選器](/help/assets/icons/Filter.svg)以切換篩選器面板的顯示。

如需詳細資訊，請參閱[篩選區段清單](t-seg-filter.md)。


<!--

The Segment Manager offers many ways of curating segments, such as sharing, filtering, tagging, approving, copying, deleting, and marking as favorites.

The Analytics Segment Manager shows you all the segments you own and that have been shared with you. Admin-level users can see all segments in the organization. This overview presents the user interface and the capabilities of the Segment Manager. 

![Segments manager](assets/segments-manager.png)

## Access the Segment Manager

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**.

   Or 

   In an existing report, select the Segments icon ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) in the left navigation, then select **[!UICONTROL Manage]**.

## Available actions in the Segment Manager

In the Segment Manager, you can:

* [Filter segments](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Approve segments](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Tag segments](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Share segments](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Export a segment to a CSV file.

* [Copy segments](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Delete segments](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configure columns

You can configure the information displayed for each segment in the Segment Manager by configuring the columns that are displayed.

To configure the visible columns in the Segment Manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Segments]**. 

1. In the Segment Manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Segment Manager.

   The following columns are available:

   | Column title | Description  |
   |---|---|
   | Title and description | These values are provided in the Segment builder. To edit the title and description, select the title link to open the Segment builder.  |
   | Favorites  | Displays star icons next to each segment, allowing you to mark segments as favorites. For more information, see [Mark segments as favorites](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Report suites  | This column indicates in which report suite the segment was last saved.  |
   | Owner  | Indicates who owns the segment. As a non-Admin, you can see only segments you own or those that were shared with you.  |
   | Tags (not checked in column selector, hence column not appearing)  | Tags that were applied to the segment, either by you or by people who shared the segment with you.  |
   | Shared with  | Lists individuals or groups (Admin only) or All (Admin only) that you shared the segment with. <p>When a segment is being shared by you or with you, a share icon displays next to the segment name.</p>|
   | Date modified  | Shows the date that the segment was last modified.  |
   | Used in | Shows where segments are currently being used, and how many times they are being used in each area. <p>For example, if the segment is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**].</p> <p>Select the value in this column to see the breakdown of where the segments are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Alerts (2)**]). Furthermore, you can view the list of items where the segments are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of segments being used in that area:</p>  <ul><li>[!UICONTROL **Projects**]<p>Contains segments that were [created in the segment builder](/help/components/segmentation/segmentation-workflow/seg-build.md) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains segments that were [created as quick segments](/help/analyze/analysis-workspace/components/segments/quick-segments.md) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Alerts**]</li><li>[!UICONTROL **Calculated metrics**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a segment includes another segment in its definition, any use of that segment is not shown in the [!UICONTROL **Used in**] column. If a segment is included in the definition of another type of component (such as a calculated metric), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p>  |
   | Last used | Shows the date when the segment was last used in any of the following component types: <ul><li>Alerts</li><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li><li>Segments</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |
   
   {style="table-layout:auto"}

## How-To Video {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

This [Adobe Analytics video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html) gives a short overview of how to use the Segment Manager.

-->