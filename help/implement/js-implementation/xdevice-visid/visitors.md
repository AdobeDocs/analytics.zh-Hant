---
description: Analytics 會將每個唯一的有效訪客 ID 計為獨特訪客。
keywords: Analytics 實作
seo-description: Analytics 會將每個唯一的有效訪客 ID 計為獨特訪客。
seo-title: 訪客
solution: Analytics
subtopic: 訪客
title: 訪客
topic: 開發人員和實作
uuid: 16cfdb64-a3c6-4056-97da-3227cddcf1cd
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 訪客

>[!IMPORTANT]
>
>不建議您繼續使用這種跨裝置識別訪客的方法。請參閱 [Adobe Experience cloud裝置合作檔案](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

Analytics 會將每個唯一的有效訪客 ID 計為獨特訪客。

如果您查看[上表](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA)，則會發現這已發生 3 次: 在點擊 1、9 和 10。之所以會如此，是因為這兩個伺服器呼叫的有效[!UICONTROL 訪客 ID] 是相同的，即使訪客相隔了數小時，且使用的是不同的裝置，仍是如此。

這在跨裝置訪客身分識別啟用時，可能會增加獨特訪客的數目。訪客的同一次瀏覽可能會計數兩次: 一次是初次瀏覽時，另一次是使用者完成驗證時。

當新的訪客瀏覽您的網站時，會填入並儲存 `s_vi` Cookie。資料收集伺服器會為此訪客 ID 建立新的訪客資料，並在此資料中設定有效[!UICONTROL 訪客 ID]，以符合 Cookie。

在跨裝置訪客身分識別啟用時，若在後續的點擊 (例如在驗證之後) 中提供[!UICONTROL 訪客 ID] 變數，則會更新有效[!UICONTROL 訪客 ID] 以符合自訂值。這可能會導致有效[!UICONTROL 訪客 ID] 在驗證之後隨即變更，而產生多個訪客計數。

![](assets/visitors.png)

在初次產生關聯後，瀏覽計數會恢復正常，因為訪客是透過[!UICONTROL 訪客 ID] Cookie 產生關聯的。若訪客稍後檢視了您的網站，然後進行驗證，訪客計數並不會不實膨脹，因為有效[!UICONTROL 訪客 ID] 在驗證之後並未變更。

![](assets/visitors_2.png)

