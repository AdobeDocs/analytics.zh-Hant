---
title: 串流媒體服務視訊中繼資料維度
description: 為報表套裝啟用[!UICONTROL 視訊中繼資料]時可用的維度。
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 6%

---

# 串流媒體服務視訊中繼資料維度

*此頁面說明您為報表套裝啟用[!UICONTROL 視訊中繼資料]時可用的維度。 如需可用的量度，請參閱[串流媒體服務視訊中繼資料量度](../metrics/sm-video-metadata.md)。*

串流媒體服務和維度透過串流媒體服務收集程式庫，為資料收集提供補充報告功能。 使用這些維度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[視訊中繼資料](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)時，可以使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 廣告載入 | 已載入的廣告型別。 | 待定 | `a.media.adLoad` |
| 時段 | 內容播出或播放的當天時間。 支援任何字串值。 | 媒體開始、媒體關閉 | `a.media.dayPart` |
| 集數 | 集數。 | 媒體開始、媒體關閉 | `a.media.episode` |
| 媒體摘要型別 | 摘要型別。 | 媒體開始、媒體關閉 | `a.media.feed` |
| 類型 | 內容製作者定義的內容型別或群組。 此維度支援多個值，並以逗號分隔。 | 媒體開始、媒體關閉 | `a.media.genre` |
| MVPD | Adobe驗證提供的MVPD。 | 媒體開始、媒體關閉 | `a.media.pass.mvpd` |
| 網路 | 網路或頻道名稱 | 媒體開始、媒體關閉 | `a.media.network` |
| 季數 | 此演出節目所屬的季數。 | 媒體開始、媒體關閉 | `a.media.season` |
| 節目 | 節目或影集名稱。 | 媒體開始、媒體關閉 | `a.media.show` |
| 節目類型 | 代表內容型別的整數。<br>`0`：全集<br>`1`：預覽或預告<br>`2`：片段<br>`3`：其他 | 媒體開始、媒體關閉 | `a.media.type` |

{style="table-layout:auto"}
