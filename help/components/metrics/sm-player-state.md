---
title: 串流媒體服務播放器狀態追蹤量度
description: 當您為報表套裝啟用[!UICONTROL 播放器狀態追蹤]時可用的量度。
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 1%

---

# 串流媒體服務播放器狀態追蹤量度

串流媒體服務播放器狀態追蹤量度透過串流媒體服務程式庫，提供資料收集的補充報告功能。 使用這些量度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media廣告]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[播放器狀態追蹤](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列量度：

| 量度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 受隱藏式字幕影響的資料流 | 在播放工作階段期間發生至少一個隱藏式字幕狀態時觸發。 | 媒體關閉 | `a.media.states.closedcaptioning.set` |
| 隱藏式字幕次數 | 視訊進入隱藏式字幕狀態的次數。 | 媒體關閉 | `a.media.states.closedcaptioning.count` |
| 隱藏式字幕總時間 | 視訊處於隱藏式字幕狀態的時間（以秒為單位）。 | 媒體關閉 | `a.media.states.closedcaptioning.time` |
| 受全熒幕影響的資料流 | 在播放工作階段期間發生至少一個全熒幕狀態時觸發。 | 媒體關閉 | `a.media.states.fullscreen.set` |
| 全熒幕次數 | 視訊進入全熒幕狀態的次數。 | 媒體關閉 | `a.media.states.fullscreen.count` |
| 全熒幕總時間 | 視訊處於全熒幕狀態的時間長度，以秒為單位。 | 媒體關閉 | `a.media.states.fullscreen.time` |
| 受觀看中影響的資料流 | 在播放工作階段期間發生至少一個觀看中狀態時觸發。 | 媒體關閉 | `a.media.states.infocus.set` |
| 觀看中次數 | 影片進入觀看中狀態的次數。 | 媒體關閉 | `a.media.states.infocus.count` |
| 觀看中總時間 | 視訊處於觀看中狀態的時間長度，以秒為單位。 | 媒體關閉 | `a.media.states.infocus.time` |
| 受靜音影響的資料流 | 在播放工作階段期間發生至少一個靜音狀態時觸發。 | 媒體關閉 | `a.media.states.mute.set` |
| 靜音次數 | 視訊進入「靜音」狀態的次數。 | 媒體關閉 | `a.media.states.mute.count` |
| 靜音總時間 | 視訊處於靜音狀態的時間長度，以秒為單位。 | 媒體關閉 | `a.media.states.mute.time` |
| 受子母畫面影響的資料流 | 如果在播放工作階段期間發生至少一個子母畫面狀態，則會觸發。 | 媒體關閉 | `a.media.states.pictureinpicture.set` |
| 子母畫面次數 | 視訊進入「子母畫面」狀態的次數。 | 媒體關閉 | `a.media.states.pictureinpicture.count` |
| 子母畫面總時間 | 視訊處於子母畫面狀態的時間長度（以秒為單位）。 | 媒體關閉 | `a.media.states.pictureinpicture.time` |

{style="table-layout:auto"}
