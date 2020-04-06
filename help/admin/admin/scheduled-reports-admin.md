---
description: 讓管理員層級使用者查看與管理組織中的排程報表。
title: 排程報表佇列
topic: Reports
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 排程報表佇列

讓管理員層級使用者查看與管理組織中的排程報表。

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**

「排程報表管理員」中的管理層級功能包含：

* 在組織中顯 [示所有計畫報表](/help/admin/admin/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) 的選項。
* [組織中的進階篩選功能](/help/admin/admin/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) 。
* 新的「報 [告佇列](/help/admin/admin/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) 」標籤會列出報告伺服器上佇列等候執行的所有報告。
* 在「報 [表佇列](/help/admin/admin/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) 」介面中公開「排程ID」。

## Show all Scheduled Reports {#section_3F167CAAEEC24140B476CF95B7402690}

在標 **[!UICONTROL Report List]** 簽上，除了您個 **[!UICONTROL Show All Scheduled Reports]** 人排程的選項外，您還可以在組織中。

>[!NOTE] 此 **[!UICONTROL Report Name]** 欄會顯示排程中報表的名稱，而此欄會顯示您 **[!UICONTROL File Name]** 在進階傳送選項中設定的任何自訂檔案名稱。 因此，如果您排程多個相同報表類型的報表，並指定每個報表的自訂名稱，「排程報表管理員」會顯示多個具有相同報表名稱但檔案名稱不同的項目。 這是因為排程的後端報表相同，因此「報表名稱」欄除了自訂檔案名稱（如設定）外，所有報表名稱都相同。

![](assets/show_all_scheduled_reports.png)

## 進階篩選功能 {#section_206A52A85DE84947AAB3AD082FBF6275}

For example, if you wanted to filter on all reports that are scheduled hourly, you would specify **[!UICONTROL Frequency equals Hourly]** in the **[!UICONTROL Advanced]** filter and click **[!UICONTROL Apply]**:

![](assets/advanced_filtering_schedl_reports.png)

## 報表佇列 {#section_03C866115D354BB182E90BF4D52F1E0B}

此佇列可讓您管理並潛在刪除任何「堵塞」佇列的排程報表。 （通常，報告會在4小時後逾時。）

![](assets/scheduled_reports_2.png)

「報表佇列」也可讓您「略過計畫報表一次」。 Just click the blue icon in the **[!UICONTROL Manage]** column.

## 排程 ID {#section_568B70F4228C4229977CB85D2DCD53A1}

Having the **[!UICONTROL Schedule ID]** exposed in the Report Queue interface helps when you need to contact Adobe Client Care for resolution of a scheduled reports issue.

![](assets/schedule_id.png)
