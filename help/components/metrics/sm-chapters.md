---
title: 串流媒體服務章節量度
description: 為報表套裝啟用[!UICONTROL 媒體章節]時可用的量度。
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 5%

---

# 串流媒體服務章節量度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體章節]時可用的量度。 如需可用的維度，請參閱[串流媒體服務章節維度](../dimensions/sm-chapters.md)。*

串流媒體服務章節量度透過串流媒體服務收集程式庫，為資料收集提供補充報告功能。 使用這些量度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media廣告]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[媒體章節](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列量度：

| 量度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 章節完成 | 在章節完成時觸發的布林值。 | 章節關閉 | `a.media.chapter.complete` |
| 章節開始 | 在章節開始時觸發的布林值。 | 章節開始 | `a.media.chapter.view` |
| 章節逗留時間 | 在章節逗留的時間量（以秒為單位）。 | 章節關閉 | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
