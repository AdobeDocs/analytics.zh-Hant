---
title: 串流媒體服務廣告維度
description: 為報表套裝啟用[!UICONTROL 媒體廣告]時可用的維度。
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 4%

---

# 串流媒體服務廣告維度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體廣告]時可用的維度。 如需可用的量度，請參閱[串流媒體廣告量度](../metrics/sm-ads.md)。*

串流媒體服務和維度透過串流媒體服務程式庫，為資料收集提供補充報表功能。 使用這些維度需要&#x200B;**[!UICONTROL 適用於串流媒體的Adobe Analytics附加元件]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[媒體廣告](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 | XDM欄位 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 廣告]** | 廣告的唯一識別碼。 | 廣告開始、廣告關閉 | `a.media.ad.`<br>`name` | `xdm.mediaCollection.`<br>`advertisingDetails.name`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.name` |
| **[!UICONTROL 廣告名稱（變數）]** | 廣告的易記名稱。 名為&#39;[!UICONTROL 廣告名稱]&#39;的分類維度也可供使用，可提供類似的用途。 此維度和分類會被視為兩個不同的維度。 | 廣告開始、廣告關閉 | `a.media.ad.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`advertisingDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.friendlyName` |
| **[!UICONTROL 廣告播放器名稱]** | 轉譯廣告之播放器的名稱。 | 廣告開始、廣告關閉 | `a.media.ad.`<br>`playerName` | `xdm.mediaCollection.`<br>`advertisingDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.playerName` |
| **[!UICONTROL 廣告長度（變數）]** | 視訊廣告的長度（以秒為單位）。 | 廣告開始、廣告關閉 | `a.media.ad.`<br>`length` | `xdm.mediaCollection.`<br>`advertisingDetails.length`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.length` |
| **[!UICONTROL 廣告Pod]** | 廣告Pod的唯一識別碼。 | 廣告開始、廣告關閉 | `a.media.ad.`<br>`pod` | |
| Pod位置中的&#x200B;**[!UICONTROL 廣告]** | 上層廣告插播內的廣告索引位置（0索引）。 | 廣告開始、廣告關閉 | `a.media.ad.`<br>`podPosition` | `xdm.mediaCollection.`<br>`advertisingDetails.podPosition`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.podPosition` |
| **[!UICONTROL 廣告商]** | 廣告中介紹的公司或品牌。 | 廣告開始、廣告關閉 | `a.media.ad.`<br>`advertiser` | `xdm.mediaCollection.`<br>`advertisingDetails.advertiser`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.advertiser` |
| **[!UICONTROL 行銷活動 ID]** | 廣告促銷活動 ID | 廣告開始、廣告關閉 | `a.media.ad.`<br>`campaign` | `xdm.mediaCollection.`<br>`advertisingDetails.campaignID`<br><br>`xdm.mediaReporting.`<br>`advertisingDetails.campaignID` |

除了上述維度之外，Adobe會自動建立下列分類維度。 您必須上傳分類資料，才能檢視使用這些維度的報表。

| 分類名稱 | 父維度 | 說明 |
| --- | --- | --- |
| **[!UICONTROL 資產ID]** | [[!UICONTROL 內容]](sm-core.md) | 媒體資產內容的唯一識別碼。 例如電視影集集數識別碼、電影資產識別碼，或即時事件識別碼。 這些ID通常衍生自中繼資料授權單位，例如EIDR、TMS/Gracenote、Rovi，或衍生自其他專屬或內部系統。 |
| **[!UICONTROL 內容評等]** | [[!UICONTROL 內容]](sm-core.md) | 依美國電視分級制度(TV Parental Guidelines)的定義進行分級。 |
| **[!UICONTROL 首播日期]** | [[!UICONTROL 內容]](sm-core.md) | 內容在電視上的首播日期。 由於此分類維度是字串，因此允許任何日期格式。 Adobe建議使用一致的日期格式，例如`YYYY-MM-DD`。 |
| **[!UICONTROL 第一個數位日期]** | [[!UICONTROL 內容]](sm-core.md) | 內容在任何數位頻道或平台上的首播日期。 由於此分類維度是字串，因此允許任何日期格式。 Adobe建議使用一致的日期格式，例如`YYYY-MM-DD`。 |
| **[!UICONTROL 廣告長度]** | [!UICONTROL 廣告] | 視訊廣告的長度（以秒為單位）。 |
| **[!UICONTROL 廣告名稱]** | [!UICONTROL 廣告] | 廣告的易記名稱。 此分類等同於&#39;[!UICONTROL 廣告名稱（變數）]&#39;。 |
| **[!UICONTROL Creative ID]** | [!UICONTROL 廣告] | 廣告創意的ID。 |
| **[!UICONTROL Pod名稱]** | [!UICONTROL 廣告Pod] | 廣告Pod的易記名稱。 |
| **[!UICONTROL Pod位置]** | [!UICONTROL 廣告Pod] | 內容內的廣告插播位移（以秒為單位）。 |
