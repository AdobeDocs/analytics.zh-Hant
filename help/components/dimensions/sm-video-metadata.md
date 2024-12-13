---
title: 串流媒體視訊中繼資料維度
description: 為報表套裝啟用[!UICONTROL 視訊中繼資料]時可用的維度。
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 7%

---

# 串流媒體視訊中繼資料維度

*此頁面說明您為報表套裝啟用[!UICONTROL 視訊中繼資料]時可用的維度。 如需可用的量度，請參閱[串流媒體視訊中繼資料量度](../metrics/sm-video-metadata.md)。*

串流媒體廣告維度透過串流媒體收集程式庫提供資料收集的補充報告功能。 使用這些維度需要&#x200B;**[!UICONTROL Adobe串流媒體集合]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在[媒體報告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下啟用&#x200B;**[!UICONTROL 視訊中繼資料]**&#x200B;時，可以使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 廣告載入 | 已載入的廣告型別。 | 待定 | `a.media.adLoad` |
| 時段 | 內容播出或播放的當天時間。 支援任何字串值。 | 媒體開始、媒體關閉 | `a.media.dayPart` |
| 集數 | 集數。 | 媒體開始、媒體關閉 | `a.media.episode` |
| 媒體摘要型別 | 摘要型別。 | 媒體開始、媒體關閉 | `a.media.feed` |
| 類型 | 內容製作者定義的內容型別或群組。 此維度支援多個值，並以逗號分隔。 | 媒體開始、媒體關閉 | `a.media.genre` |
| MVPD | 由Adobe驗證提供的MVPD。 | 媒體開始、媒體關閉 | `a.media.pass.mvpd` |
| 網路 | 網路或頻道名稱 | 媒體開始、媒體關閉 | `a.media.network` |
| 季數 | 此演出節目所屬的季數。 | 媒體開始、媒體關閉 | `a.media.season` |
| 節目 | 節目或影集名稱。 | 媒體開始、媒體關閉 | `a.media.show` |
| 節目類型 | 代表內容型別的整數。<br>`0`：全集<br>`1`：預覽或預告<br>`2`：片段<br>`3`：其他 | 媒體開始、媒體關閉 | `a.media.type` |

{style="table-layout:auto"}
