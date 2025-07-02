---
description: 瞭解如何管理警報。
title: 管理警報
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 24dd47e995523aedba1385ee8882af5e11c7b128
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 22%

---


# 管理警報


您可以從中央[!UICONTROL 警示]管理介面篩選、標籤、刪除、重新命名、複製、啟用、停用、更新及匯出警示。 若要管理警報：

* 在主介面中選取&#x200B;**[!UICONTROL 元件]**，然後選取&#x200B;**[!UICONTROL 警示]**。

警報管理員的結構類似於[區段管理員](/help/components/segmentation/segmentation-workflow/seg-manage.md)和[計算量度管理員](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)。


## 警報管理器

「警報」管理員具有下列介面元素：

![篩選器介面](assets/alerts-manager.png)

### 警示清單

警示清單➊會顯示您擁有的所有警示、已涵蓋您所有專案的警示，以及已與您共用的警示。 清單有以下欄位：

| 欄 | 說明 |
|---|---|
| ![StarOutline](/help/assets/icons/StarOutline.svg) | 選取以偏好![Star](/help/assets/icons/Star.svg)或取消偏好![StarOutline](/help/assets/icons/StarOutline.svg)警報。 |
| **[!UICONTROL 標題和說明]** | 若要編輯警報，請選取標題連結，以開啟[警報產生器](alert-builder.md#alert-builder)。 |
| **[!UICONTROL 類型]** | 警報型別： Adobe Analytics資料警報或伺服器呼叫使用量警報。 |
| **[!UICONTROL 已啟用]** | 警報已啟用或已停用。 |
| **[!UICONTROL 報告套裝]** | 套用此警報的報告套裝。 |
| **[!UICONTROL 所有者]** | 警示的擁有者。 如果您不是管理員，您只會看到自己擁有的警示或與您共用的警示。 |
| **[!UICONTROL 標記]** | 此警示的標籤。 |
| **[!UICONTROL 過期日期]** | 警示設為到期的日期和時間。 |
| **[!UICONTROL 修改日期]** | 上次修改警示的日期和時間。 |

<!-- 

When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul>

-->

使用![ColumnSetting](/help/assets/icons/ColumnSetting.svg)指定要顯示的欄位。

### 動作列

您可以使用動作列➋對警示執行動作。 動作列包含以下動作：

| 圖示 | 動作 | 說明 |
|:---:|---|---|
| ![AddCircle](/help/assets/icons/AddCircle.svg) | **[!UICONTROL 新增]** | 使用[警報產生器](alert-builder.md#alert-builder)新增另一個警報。 |
| ![Search](/help/assets/icons/Search.svg) | [!UICONTROL *依標題搜尋*] | 當清單中未選取警示時，請使用此搜尋欄位來搜尋警示。 |
| ![Label](/help/assets/icons/Label.svg) | **[!UICONTROL 標記]** | 標籤選取的警報。 在&#x200B;**[!UICONTROL 標籤警示]**&#x200B;對話方塊中，選取或取消選取所選警示的標籤。 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存所選警示的標籤。 |
| ![Delete](/help/assets/icons/Delete.svg) | **[!UICONTROL 刪除]** | 刪除選取的警示。 系統會提示您進行確認。 |
| ![Edit](/help/assets/icons/Edit.svg) | **[!UICONTROL 重新命名]** | 重新命名單一選取的警報。 選取後，您可以重新命名內嵌警報。 |
| ![Copy](/help/assets/icons/Copy.svg) | **[!UICONTROL 複製]** | 複製選取的警報。 已建立具有相同名稱與尾碼`(Copy)`的新警示。 |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL 啟用]**&#x200B;或&#x200B;**[!UICONTROL 停用]** | 啟用或停用選取的警示。 |
| ![重新整理](/help/assets/icons/Refresh.svg) | **[!UICONTROL 續約]** | 續約警報的到期日。無論原始到期日為何，到期日都會從您選取此選項的當天算起延長1年。 |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL 匯出至 CSV]** | 將警示匯出至`Alerts List.csv`檔案。 |


### 使用中的篩選欄

篩選器列➌顯示從篩選器面板套用至警示清單的作用中篩選器（如果有的話）。 您可以使用![CrossSize75](/help/assets/icons/CrossSize75.svg)快速移除篩選條件。如果指定多個篩選條件，您可以使用&#x200B;**[!UICONTROL 移除全部]**&#x200B;來移除所有篩選條件。


### 篩選面板

您可以使用![篩選器](/help/assets/icons/Filter.svg) **[!UICONTROL 篩選器]**&#x200B;左側面板➍來篩選警示清單。 篩選器面板會顯示篩選器的型別，以及遵循特定篩選器的警示數目。


1. 選取![Filter](/help/assets/icons/Filter.svg)開啟「篩選」面板。如果您需要更多空間以儲存警示清單，可以再次選取![篩選器](/help/assets/icons/Filter.svg)以關閉面板。
1. 從任何可用的篩選器區段中選取篩選器。


#### 標籤篩選區段

{{tagfiltersection}}


#### 報表套裝篩選區段

{{reportsuitefiltersection}}


#### 「擁有者」篩選器區段

{{ownerfiltersection}}


#### 啟用狀態過濾器區段

{{enabledstatusfiltersection}}


#### 類型篩選器區段

{{typefiltersection}}


#### 其他篩選器篩選區段

{{otherfiltersfiltersection}}



## 編輯警報

您可以編輯警報

* 在[[!UICONTROL 警示]清單](#alerts-list)中，選取警示的標題。

您使用[警報產生器](alert-builder.md#alert-builder)來編輯警報。

## 疑難排解警報

對警報問題進行疑難排解時，請向Adobe支援提供JID （工作執行個體ID）編號。 JID號碼位於您收到的警報電子郵件通知底部。

![警報電子郵件](assets/alerts-email.PNG)


<!--

# Manage alerts

You can manage existing alerts in the Alerts manager. You can perform various management tasks on alerts, such as tagging, renaming, deleting, and more.

The Alerts manager is structured very much like the [Segment Manager](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=zh-Hant) and the [Calculated Metric Manager](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=zh-Hant).

 ![](assets/alert-manager.png)

## Create alerts

To create alerts from the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select [!UICONTROL **Add**] (or [!UICONTROL **Create new alert**] if you don't have any existing alerts).

1. Select the alert type that corresponds to the alert that you want to create:

   * [!UICONTROL **Analytics data alert**]: An alert to notify you when abnormal events occur in your data. 

     If you select this option, continue with [Create alerts](/help/components/c-alerts/alert-builder.md) for more details about creating alerts.

   * [!UICONTROL **Server call usage alert**]: An alert to notify you of the risk or occurrence of an overage in your server call consumption and commitment data. 

     If you select this option, continue with [Server call usage alerts](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >You must be an Analytics administrator or a user with the Server call usage permission in order to have access to server call usage. 

## Manage existing alerts

You can perform various actions on existing alerts, such as tagging, renaming, deleting, and so forth.

To manage existing alerts in the Alerts manager:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select one or more alerts that you want to manage.

   ![](assets/alert-manager-tasks.png)

1. In the action bar, select any of the following options:

   | Action | Function | 
   |---------|----------|
   | [!UICONTROL **Tag**] | Apply a tag to an alert. This helps you to organize alerts for ease of use. | 
   | [!UICONTROL **Delete**] | Deletes the alert. | 
   | [!UICONTROL **Rename**] | Renames the alert. |
   | [!UICONTROL **Approve**] | Mark the alert as Approved. |
   | [!UICONTROL **Copy**] | Creates a copy (duplicate) of the alert. |
   | [!UICONTROL **Disable**] | Disables an alert that is currently enabled. |
   | [!UICONTROL **Enable**] | Enables an alert that is currently disabled. |
   | [!UICONTROL **Renew**] | Renews the alert expiration date. This extends the  expiration date to be 1 year from the day you selected this option, regardless of the original expiration date. |
   | [!UICONTROL **Export to CSV**] | Exports the alert to a .CSV file. |

## Edit an alert

To edit an existing alert:

1. Select **[!UICONTROL Components]** > **[!UICONTROL Alerts]** to access the Alerts manager in Adobe Analytics.

   ![](assets/alert-manager.png)

1. Select the alert name in the [!UICONTROL **Title and description**] column.

1. Edit the alert as desired. 

   Following are some of the things you can do when editing an alert:

   * Add alerts to other report suites
   * Add or modify the description
   * Modify the time granularity
   * Modify the recipients 
   * Modify the expiration date
   * Modify the metrics and filters

1. Select [!UICONTROL **Save**].

## Configure columns 

You can configure the information displayed for each alert in the Alerts manager by configuring the columns that are displayed.

To configure the visible columns in the Alerts manager:

1. In Adobe Analytics, select the **[!UICONTROL Components]** tab, then select **[!UICONTROL Alerts]**. 

1. In the Alert manager, select the **Customize columns** icon ![Customize columns icon](assets/customize-columns-icon.png), then select the columns that you want to be displayed in the Alerts manager.

   The following columns are available:

   | Column title  | Description |
   |---|---|
   | Title and description | These values are provided in the Alert builder. To edit the title and description, select the title link to open the Alert builder.  |
   | Favorites  | Displays star icons next to each alert, allowing you to mark alerts as favorites. |
   | Type | Shows whether the alert is an Analytics data alert or a Server call usage alert. |
   | Enabled | Shows whether the alert is currently enabled or disabled. | 
   | Report suite | Indicates in which report suite the alert was last saved.  |
   | Owner | Indicates who owns the alert. As a non-admin, you can see only alerts you own or those that were shared with you.  |
   | Tags | Shows tags that were applied to the alert, either by you or by people who shared the alert with you.  |
   | Expiration date | Shows the date and time when the alert is set to expire. |
   | Date modified | Indicates the date when the alert was last modified.  |

   {style="table-layout:auto"}
   
   
    When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> 
   
-->

