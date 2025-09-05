---
title: 串流媒體服務廣告維度
description: 為報表套裝啟用[!UICONTROL 媒體廣告]時可用的維度。
feature: Dimensions
exl-id: 3f17bacc-8c36-499a-a863-9298e2d54370
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 15%

---

# 串流媒體服務廣告維度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體廣告]時可用的維度。 如需可用的量度，請參閱[串流媒體廣告量度](../metrics/sm-ads.md)。*

串流媒體服務和維度透過串流媒體服務程式庫，為資料收集提供補充報表功能。 使用這些維度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[媒體廣告](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 廣告 | 廣告的唯一識別碼。 | 廣告開始、廣告關閉 | `a.media.ad.name` |
| 廣告名稱（變數） | 廣告的易記名稱。 名為「廣告名稱」的分類維度也可供使用，其用途類似。 此維度和分類會被視為兩個不同的維度。 | 廣告開始、廣告關閉 | `a.media.ad.friendlyName` |
| 廣告播放器名稱 | 轉譯廣告之播放器的名稱。 | 廣告開始、廣告關閉 | `a.media.ad.playerName` |
| 廣告長度（變數） | 視訊廣告的長度（以秒為單位）。 | 廣告開始、廣告關閉 | `a.media.ad.length` |
| 廣告Pod | 廣告Pod的唯一識別碼。 | 廣告開始、廣告關閉 | `a.media.ad.pod` |
| Pod位置中的廣告 | 上層廣告插播內的廣告索引位置（0索引）。 | 廣告開始、廣告關閉 | `a.media.ad.podPosition` |
| 廣告商 | 廣告中介紹的公司或品牌。 | 廣告開始、廣告關閉 | `a.media.ad.advertiser` |
| 行銷活動 ID | 廣告促銷活動 ID | 廣告開始、廣告關閉 | `a.media.ad.campaign` |

{style="table-layout:auto"}

除了上述維度之外，Adobe會自動建立下列分類維度。 您必須上傳分類資料，才能檢視使用這些維度的報表。

| 分類名稱 | 父維度 | 說明 |
| --- | --- | --- |
| 資產 ID | [內容](sm-core.md) | 媒體資產內容的唯一識別碼。 例如電視影集集數識別碼、電影資產識別碼，或即時事件識別碼。 這些ID通常衍生自中繼資料授權單位，例如EIDR、TMS/Gracenote、Rovi，或衍生自其他專屬或內部系統。 |
| 內容分級 | [內容](sm-core.md) | 依美國電視分級制度(TV Parental Guidelines)的定義進行分級。 |
| 首播日期 | [內容](sm-core.md) | 內容在電視上的首播日期。由於此分類維度是字串，因此允許任何日期格式。 Adobe建議使用一致的日期格式，例如`YYYY-MM-DD`。 |
| 首次數位化日期 | [內容](sm-core.md) | 內容在任何數位頻道或平台上的首播日期。由於此分類維度是字串，因此允許任何日期格式。 Adobe建議使用一致的日期格式，例如`YYYY-MM-DD`。 |
| 廣告長度 | 廣告 | 視訊廣告的長度（以秒為單位）。 |
| 廣告名稱 | 廣告 | 廣告的易記名稱。 此分類相當於「廣告名稱（變數）」。 |
| 創作 ID | 廣告 | 廣告創意的ID。 |
| Pod名稱 | 廣告Pod | 廣告Pod的易記名稱。 |
| Pod位置 | 廣告Pod | 內容內的廣告插播位移 (以秒數計)。 |

{style="table-layout:auto"}
