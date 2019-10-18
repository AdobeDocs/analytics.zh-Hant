---
description: 說明權限設定方式以及 Analytics 提供的維度。
seo-description: 說明權限設定方式以及 Analytics 提供的維度。
seo-title: '[!DNL Activity Map] Analytics中的報告'
solution: Analytics
title: '[!DNL Activity Map] Analytics中的報告'
topic: Activity Map
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# [!DNL Activity Map] Analytics中的報表功能

說明權限設定方式以及 Analytics 提供的維度。

## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Before users can report on [!DNL Activity Map] dimensions, you as the Admin need to

* [將用戶添加到[!DNL Activity Map]訪問組](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)。
* 將您希望存取的報表套裝新增至此群組。Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL [!DNL Activity Map]Access]** &gt; **[!UICONTROL Edit]**.
* 自訂使用者存取維度的權限。請參閱以下小節。

## 分析維 [!DNL Activity Map] 度 {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

您可以精細地[自訂使用者存取維度的權限](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html)。Here are the [!DNL Activity Map] dimensions available in Analytics:

| 維度 | 說明 |
|---|---|
| [!DNL Activity Map] 頁面 | 列出使用者在其中點按了連結的頁面。 |
| [!DNL Activity Map] 地區 | 列出整個網站上所有收集的連結地區。請注意，如果某個地區重複出現在多個頁面，則會在所有頁面上彙總此量度。 |
| [!DNL Activity Map] 連結 | 列出整個網站上所有收集的連結。 |
| [!DNL Activity Map] 連結與地區 | 列出整個網站上所有收集的連結及其地區。 |
| [!DNL Activity Map] XY | 未使用 |

* 您應可在 Analysis Workspace、Reports &amp; Analytics 以及 Report Builder 中使用這些維度，前提是您的 Analytics 實作 [enabled for [!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports &amp; Analytics, navigate to **[!UICONTROL View All Reports]** &gt; **[!UICONTROL [!DNL Activity Map]]**.

* To look at a link and region for a specific page, all you need to do is create a breakdown from the desired [!DNL Activity Map] page into the [!DNL Activity Map] Links &amp; Region.

