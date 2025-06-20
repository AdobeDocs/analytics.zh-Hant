---
description: 「計算量度」頁面提供許多管理量度的方式，例如共用、篩選、標籤、核准、複製、刪除和標示為我的最愛。
title: 計算量度管理器
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: 9714863374052e257e1d6349c442fc74182a0a2f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 29%

---

# 管理計算量度

您可以從中央的[!UICONTROL 計算量度]管理介面共用、篩選、標籤、核准、重新命名、複製、刪除、匯出計算量度，以及將計算量度標示為我的最愛。 若要管理計算量度：


* 在主介面中選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 計算量度]**。


## 計算量度管理器

計算量度管理員具有下列介面元素：


![計算量度介面](assets/calculated-metrics-manager.png)

### 計算量度清單

計算量度清單➊會顯示您所擁有或已與您共用的所有計算量度。 清單有以下欄位：

<!-- I think this table incorrectly talks about quick calculated metrics -->

| 欄 | 說明 |
| --- | --- | 
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 選取以偏好![Star](/help/assets/icons/Star.svg)或取消偏好![StarOutline](/help/assets/icons/StarOutline.svg)計算量度。 檢視[將計算量度標示為我的最愛](cm-favorite.md) |
| **[!UICONTROL 標題和說明]** | 若要編輯計算量度，請選取標題連結，以開啟[計算量度產生器](c-build-metrics/cm-build-metrics.md)。 共用計算量度以![共用](/help/assets/icons/ShareAlt.svg)表示。 |
| **[!UICONTROL 報告套裝]** | 套用此計算量度的報表套裝。 |
| **[!UICONTROL 所有者]** | 計算量度的擁有者。 做為使用者，您只能看到您擁有的註解或與您共用的註解。 |
| **[!UICONTROL 標記]** | 列出此計算量度的標籤。 |
| **[!UICONTROL 共用對象]** | 列出您與之共用計算量度的個人或群組數。 選取以開啟&#x200B;**[!UICONTROL 共用計算量度]**&#x200B;對話方塊。 如需詳細資訊，請參閱[共用計算量度](cm-sharing.md)。 |
| **[!UICONTROL 修改日期]** | 上次修改計算量度的日期和時間。 |
| **[!UICONTROL 使用於]** | 顯示目前使用計算量度的位置，以及在每個區域中使用計算量度的次數。 <p>例如，如果計算量度用於40個專案和2個警示，則此欄的值會顯示為&#x200B;[!UICONTROL **42個元件**]。 <p>選取此欄中的值，以檢視使用計算量度的明細(例如，[!UICONTROL **專案(40)**]、[!UICONTROL **行動計分卡(2)**])。 此外，您也可以檢視使用計算量度的專案清單。 例如，若要查看正在使用篩選器的專案清單，請選取「[!UICONTROL **專案 (40)**]」連結。</p><p>以下每個區域都會顯示該區域內使用的計算量度例項數：</p> <ul><li>[!UICONTROL **專案**]<p>包含[在計算量度產生器](c-build-metrics/cm-build-metrics.md)中建立且可用於所有專案的計算量度。</p></li><li>[!UICONTROL **臨時元件**]<p>包含[建立為快速計算量度](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project)的計算量度，且僅適用於單一專案。</p></li><li>[!UICONTROL **已排程的專案**]</li><li>[!UICONTROL **行動計分卡**]</li><li>[!UICONTROL **註解**]</li><li>[!UICONTROL **Report Builder**]<p>選取此選項可下載包含下列資料欄的CSV檔案：</p><ul><li>Report Builder 名稱</li><li>最後存取時間</li><li>最後存取的 IMS 使用者 ID</li><li>最後存取的使用者名稱</li></ul></li></ul><p>此資訊可協助您判斷元件是否對貴組織中的使用者有價值、元件使用位置以及元件是否需要刪除或修改。</p><p>檢視此欄時請考慮以下事項：</p><ul><li>此資訊僅適用於系統管理員。</li><li>依預設，「[!UICONTROL **使用於**]」欄不會顯示。使用 ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) 來設定此欄的顯示。</li><li>此資訊不包括 API 或 Data Warehouse 的使用情況。</li><li>如果此欄中沒有指定元件的資料，但具有&#x200B;[!UICONTROL **上次使用**]&#x200B;日期，則表示該元件可能已用於分析而未儲存。</li><li>使用情況資訊從 2023 年 9 月開始提供。</li></ul><p>您可以將[資料字典](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)與此資訊搭配使用，以協助追蹤並深入了解元件在組織中的使用情況。</p> |
| **[!UICONTROL 上次使用]** | 上次使用計算量度的時間。 |

{style="table-layout:auto"}

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要顯示的欄位。

### 動作列

您可以使用動作列➋對篩選器進行動作。 動作列包含以下動作：

| 圖示 | 動作 | 說明 |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 新增]** | 使用[計算量度產生器](c-build-metrics/cm-build-metrics.md)新增另一個計算量度。 |
| ![Search](/help/assets/icons/Search.svg) | [!UICONTROL *依標題搜尋*] | 當清單中未選取任何計算量度時，請使用此搜尋欄位搜尋篩選器。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 標記]** | 標籤所選的計算量度。 在&#x200B;**[!UICONTROL 標籤計算量度]**&#x200B;對話方塊中，選取或取消選取所選計算量度的標籤。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選計算量度的標籤。 如需詳細資訊，請參閱[標籤計算量度](cm-tagging.md)。 |
| ![Share](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL 共用]** | 共用選取的計算量度。 在&#x200B;**[!UICONTROL 共用計算量度]**&#x200B;對話方塊中，您可以![搜尋](/help/assets/icons/Search.svg) *搜尋個人或群組*，也可以選取&#x200B;**[!UICONTROL 組織]**&#x200B;或&#x200B;**[!UICONTROL 群組]**。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選計算量度的共用詳細資料。 如需詳細資訊，請參閱[共用計算量度](cm-sharing.md)。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 刪除]** | 刪除所選的計算量度。 系統會提示您進行確認。 |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 重新命名]** | 重新命名單一選取的計算量度。 選取後，您可以重新命名內嵌計算量度。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 核准]** | 核准所選的計算量度。 請參閱[核准計算量度](cm-approving.md)。 |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 複製]** | 複製所選的計算量度。 已建立具有相同名稱和尾碼的新計算量度`(Copy)` |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 匯出至 CSV]** | 將計算量度匯出至`Calculated  metric List.csv`檔案。 |

### 使用中的篩選欄

篩選器列➌顯示從篩選器面板套用至計算量度清單（如果有的話）的作用中篩選器。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速移除篩選條件。如果指定多個篩選條件，您可以使用&#x200B;**[!UICONTROL 移除全部]**&#x200B;來移除所有篩選條件。

### 篩選面板

您可以使用![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 篩選器]**&#x200B;左側面板➍來篩選計算量度清單。 篩選器面板會顯示篩選器的型別，以及遵循特定篩選器的計算量度數目。 選取「![篩選器](/help/assets/icons/Filter.svg)」以切換篩選器面板的顯示內容。

如需詳細資訊，請參閱[篩選計算量度清單](cm-filter.md)。

<!-- OLD CONTENT

The Calculated metrics page offers many ways of curating metrics, such as sharing, filtering, tagging, approving, copying, deleting, and marking as favorites.

The Calculated metrics page shows you all the segments you own and that have been shared with you. Admin-level users can see all custom metrics in the organization. 

## Access the Calculated metrics manager

1. In Adobe Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Calculated metrics**].

## Available actions in the Calculated metrics manager

In the Calculated metrics manager, you can:

* [Filter calculated metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-filter.md)

* [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md)

* [Approve calculated metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-approving.md)

* [Tag calculated metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-tagging.md)

* [Share calculated metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)

* Export a calculated metric to a CSV file. 

* [Copy calculated metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-copy.md)

* Delete calculated metrics

## Configure columns

You can configure the information displayed for each calculated metric in the Calculated metrics manager by configuring the columns that are displayed.

To configure the visible columns in the Calculated metrics manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Calculated metrics]**. 

1. In the Calculated metrics manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Calculated metrics manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Favorites  | Displays star icons next to each calculated metric, allowing you to mark calculated metrics as favorites. For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). |
   | Title and description | These values are provided in the Calculated metric builder. To edit the title and description, select the title link to open the Calculated metric builder.  |
   | Report suite | Indicates in which report suite the metric was last saved.  |
   | Owner | Indicates who owns the custom metric. As a non-admin, you can see only metrics you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the metric, either by you or by people who shared the calculated metric with you.  |
   | Shared with | Lists individuals or groups (admin only) or All (admin only) that you shared the calculated metric with. <p>When a calculated metric is being shared, a share icon displays next to the calculated metric name.</p>  |
   | Date modified | Indicates the date when the custom metric was last modified.  |
   | Used in | Shows where calculated metrics are currently being used, and how many times they are being used in each area. <p>For example, if the calculated metric is being used in 40 projects and 2 alerts, then the value of this column shows as [!UICONTROL **42 components**]. <p>Select the value in this column to see the breakdown of where the calculated metrics are being used (for example, [!UICONTROL **Projects (40)**], [!UICONTROL **Alerts (2)**]). Furthermore, you can view the list of items where the calculated metrics are being used. For example, so see the list of projects where they are being used, select the [!UICONTROL **Projects (40)**] link.</p><p>Each of the following areas shows the number of instances of calculated metrics being used in that area:</p> <ul><li>[!UICONTROL **Projects**]<p>Contains calculated metrics that were [created in the calculated metric builder](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) and are available for all projects.</p></li><li>[!UICONTROL **Ad hoc components**]<p>Contains calculated metrics that were [created as quick calculated metrics ](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) and are available only within a single project.</p></li><li>[!UICONTROL **Scheduled projects**]</li><li>[!UICONTROL **Mobile Scorecards**]</li><li>[!UICONTROL **Annotations**]</li><li>[!UICONTROL **Alerts**]</li><li>[!UICONTROL **Report Builder**]<p>Selecting this option downloads a CSV file, with the following columns of data:</p><ul><li>Report Builder Name</li><li>Last accessed</li><li>Last accessed IMS User ID</li><li>Last accessed user name</li></ul><p>When viewing information for Report Builder, usage information is available starting in September 2024.</p></li></ul><p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information is available only to system administrators.</li><li>The [!UICONTROL **Used in**] column does not display by default. [Configure columns](#configure-columns) to display it.</li><li>If a calculated metric includes another calculated metric in its definition, any use of that calculated metric is not shown in the [!UICONTROL **Used in**] column. If a calculated metric is included in the definition of another type of component (such as a segment), then usage is shown in the [!UICONTROL **Used in**] column.</li><li>This information does not include usage from the API or Data Warehouse.</li><li>If there is no data in this column for a given component but it has a [!UICONTROL **Last used**] date, the component might have been used in an analysis without being saved.</li><li>Usage information is available starting in September 2023.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization.</p> |
   | Last used | Shows the date when the calculated metric was last used in any of the following areas: <ul><li>Alerts</li><li>Calculated metrics</li><li>Projects</li><li>Scheduled projects</li></ul> <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li><li>This information is available only to system administrators.</li></ul><p>You can use the [Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) along with this information to help you keep track of and better understand how components are being used in your organization. |

   {style="table-layout:auto"}

-->