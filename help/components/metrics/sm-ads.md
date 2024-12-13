---
title: 串流媒體廣告量度
description: 為報表套裝啟用[!UICONTROL 媒體廣告]時可用的量度。
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 5%

---

# 串流媒體廣告量度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體廣告]時可用的量度。 如需可用的維度，請參閱[串流媒體廣告維度](../dimensions/sm-ads.md)。*

串流媒體廣告量度透過串流媒體收集程式庫提供資料收集的補充報告功能。 使用這些量度需要&#x200B;**[!UICONTROL Adobe串流媒體集合]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在[媒體報告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下啟用&#x200B;**[!UICONTROL 媒體廣告]**&#x200B;時，可以使用下列量度：

| 量度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 廣告完成 | 影片廣告完成時觸發。 | 廣告關閉 | `a.media.ad.complete` |
| 廣告開始 | 視訊廣告開始時觸發。 | 廣告開始 | `a.media.ad.view` |
| 廣告逗留時間 | 觀看廣告花費的總時間，以秒為單位。 | 廣告關閉 | `a.media.ad.timePlayed` |
| 媒體逗留時間 | 加總所有播放事件（主要內容和廣告內容）的事件持續時間（以秒為單位）。 | 媒體關閉 | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
