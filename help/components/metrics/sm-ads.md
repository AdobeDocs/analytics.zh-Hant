---
title: 串流媒體服務廣告量度
description: 為報表套裝啟用[!UICONTROL 媒體廣告]時可用的量度。
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# 串流媒體服務廣告量度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體廣告]時可用的量度。 如需可用的維度，請參閱[串流媒體服務廣告維度](../dimensions/sm-ads.md)。*

串流媒體服務廣告量度透過串流媒體服務程式庫，為資料收集提供補充報告功能。 使用這些量度需要&#x200B;**[!UICONTROL 適用於串流媒體的Adobe Analytics附加元件]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[媒體廣告](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列量度：

| 量度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 | XDM欄位 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 廣告完成]** | 影片廣告完成時觸發。 | 廣告關閉 | `a.media.ad.complete` | `xdm.mediaReporting.`<br>`advertisingDetails.isCompleted` |
| **[!UICONTROL 廣告開始]** | 視訊廣告開始時觸發。 | 廣告開始 | `a.media.ad.view` | `xdm.mediaReporting.`<br>`advertisingDetails.isStarted` |
| **[!UICONTROL 廣告逗留時間]** | 觀看廣告花費的總時間，以秒為單位。 | 廣告關閉 | `a.media.ad.timePlayed` | `xdm.mediaReporting.`<br>`advertisingDetails.timePlayed` |
| **[!UICONTROL 媒體逗留時間]** | 加總所有&#39;[!UICONTROL 播放]&#39;事件（主要內容和廣告內容）的事件持續時間（以秒為單位）。 | 媒體關閉 | `a.media.totalTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.totalTimePlayed` |
