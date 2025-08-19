---
title: 串流媒體服務視訊中繼資料量度
description: 當您啟用報表套裝的[!UICONTROL 視訊中繼資料]時可用的量度。
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 5%

---

# 串流媒體服務視訊中繼資料量度

*此頁面說明您為報表套裝啟用[!UICONTROL 視訊中繼資料]時可用的量度。 如需可用的維度，請參閱[串流媒體服務視訊中繼資料維度](../dimensions/sm-video-metadata.md)。*

串流媒體服務視訊中繼資料量度透過串流媒體服務程式庫，為資料收集提供補充報表功能。 使用這些量度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media廣告]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[視訊中繼資料](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)時，可以使用下列量度：

| 量度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 已驗證 | 透過Adobe驗證授權使用者時觸發的布林值。 | 媒體開始、媒體關閉 | `a.media.pass.auth` |

{style="table-layout:auto"}
