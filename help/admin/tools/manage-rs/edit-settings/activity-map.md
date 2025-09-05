---
description: 啟用維度，讓Activity Map可以收集資料。
title: Activity Map 報告
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 3%

---

# Activity Map 報告

可讓您啟用維度以搭配[Activity Map](/help/analyze/activity-map/overview.md)使用。

**[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** >選取報表套裝> **[!UICONTROL 編輯設定]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map報表]**

本檔案的本節內容著重於啟用Activity Map使用的維度。 如需有關覆蓋、實作變數和維度的詳細資訊，請參閱[Activity Map概觀](/help/analyze/activity-map/overview.md)。

當您選取&#x200B;**[!UICONTROL 啟用Activity Map報表]**&#x200B;按鈕時，會建立下列維度：

* [[!UICONTROL Activity Map連結]](/help/components/dimensions/activity-map-link.md)：被點按的連結名稱。
* [[!UICONTROL Activity Map地區]](/help/components/dimensions/activity-map-region.md)：被點按的地區名稱。
* [[!UICONTROL Activity Map頁面]](/help/components/dimensions/activity-map-page.md)：點選連結時的頁面名稱。
* [[!UICONTROL 各地區的Activity Map連結]](/help/components/dimensions/activity-map-link-by-region.md)： Activity Map連結與Activity Map地區的串連值。

啟用後，您的實作就可以開始傳送資料至這些維度，以用於[Analysis Workspace](/help/analyze/analysis-workspace/home.md)和[瀏覽器擴充功能重疊](/help/analyze/activity-map/overlay/overview.md)。

>[!NOTE]
>
>當您為報表套裝啟用Activity Map時，其將會永久啟用，而不會在未來以任何方式加以停用。
