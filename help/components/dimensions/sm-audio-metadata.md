---
title: 串流媒體服務音訊中繼資料維度
description: 為報表套裝啟用[!UICONTROL 音訊中繼資料]時可用的維度。
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 8%

---

# 串流媒體服務音訊中繼資料維度

串流媒體服務和維度透過串流媒體服務程式庫，為資料收集提供補充報表功能。 使用這些維度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報表]**&#x200B;下啟用[音訊中繼資料](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 相簿 | 相簿的名稱。 | 媒體開始、媒體關閉 | `a.media.album` |
| 藝術家 | 藝人的姓名。 | 媒體開始、媒體關閉 | `a.media.artist` |
| 作者 | 有聲書作者的姓名。 | 媒體開始、媒體關閉 | `a.media.author` |
| 標籤 | 紀錄標籤的名稱。 | 媒體開始、媒體關閉 | `a.media.label` |
| 發行者 | 音訊內容發行者的名稱。 | 媒體開始、媒體關閉 | `a.media.publisher` |
| 電台 | 廣播電台的名稱或ID。 | 媒體開始、媒體關閉 | `a.media.station` |

{style="table-layout:auto"}
