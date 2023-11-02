---
description: 說明權限設定方式以及 Analytics 提供的維度。
title: Analytics 中的 Activity Map 報表
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: 4af73d19afd8844f814aafd45153cc638aa535d6
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 92%

---

# Analytics 中的 Activity Map 報表

說明權限設定方式以及 Analytics 提供的維度。

## 設定權限 {#permissions}

在使用者可以報告 Activity Map 維度前，您必須先以管理員身分

* [將使用者新增至Activity Map Access產品設定檔](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* 自訂使用者存取維度的權限。請參閱以下小節。

## Analytics Activity Map 維度 {#dimensions}

您可以精細地[自訂使用者存取維度的權限](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html)。Analytics 中可供使用的 Activity Map 維度如下：

| 維度 | 說明 |
|---|---|
| Activity Map 頁面 | 列出使用者在其中點按了連結的頁面。 |
| Activity Map 地區 | 列出整個網站上所有收集的連結地區。請注意，如果某個地區重複出現在多個頁面，則會在所有頁面上彙總此量度。 |
| Activity Map 連結 | 列出整個網站上所有收集的連結。 |
| Activity Map 連結和地區 | 列出整個網站上所有收集的連結及其地區。 |
| Activity Map XY | 未使用 |

* 您應可在 Analysis Workspace、Reports &amp; Analytics 以及 Report Builder 中使用這些維度，前提是您的 Analytics 實作[已啟用 Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md)。
* 在 Reports &amp; Analytics 中，依序瀏覽至&#x200B;**[!UICONTROL 「檢視全部報表]** > **[!UICONTROL Activity Map」]**。
* 若想查看特定頁面的連結和地區，只需從所需 Activity Map 頁面往「Activity Map 連結和地區」建立劃分即可。
