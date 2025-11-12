---
title: 串流媒體服務播放器狀態追蹤量度
description: 當您為報表套裝啟用[!UICONTROL 播放器狀態追蹤]時可用的量度。
feature: Metrics
exl-id: 324936cc-0c7a-4710-a618-b24cc6a2c2cf
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 1%

---

# 串流媒體服務播放器狀態追蹤量度

串流媒體服務播放器狀態追蹤量度透過串流媒體服務程式庫，提供資料收集的補充報告功能。 使用這些量度需要&#x200B;**[!UICONTROL 適用於串流媒體的Adobe Analytics附加元件]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[播放器狀態追蹤](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列量度：

| 量度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 | XDM欄位 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 受隱藏式字幕影響的資料流]** | 在播放工作階段期間發生至少一個隱藏式字幕狀態時觸發。 | 媒體關閉 | `a.media.states.`<br>`closedcaptioning.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL 隱藏式字幕計數]** | 視訊進入隱藏式字幕狀態的次數。 | 媒體關閉 | `a.media.states.`<br>`closedcaptioning.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 隱藏式字幕總時間]** | 視訊處於隱藏式字幕狀態的時間（以秒為單位）。 | 媒體關閉 | `a.media.states.`<br>`closedcaptioning.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL 受全熒幕影響的資料流]** | 在播放工作階段期間發生至少一個全熒幕狀態時觸發。 | 媒體關閉 | `a.media.states.`<br>`fullscreen.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL 全熒幕次數]** | 視訊進入全熒幕狀態的次數。 | 媒體關閉 | `a.media.states.`<br>`fullscreen.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 全熒幕總時間]** | 視訊處於全熒幕狀態的時間長度，以秒為單位。 | 媒體關閉 | `a.media.states.`<br>`fullscreen.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL 受觀看中影響的資料流]** | 在播放工作階段期間發生至少一個觀看中狀態時觸發。 | 媒體關閉 | `a.media.states.`<br>`infocus.set` | `mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL 觀看中次數]** | 影片進入觀看中狀態的次數。 | 媒體關閉 | `a.media.states.`<br>`infocus.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 觀看中總時間]** | 視訊處於觀看中狀態的時間長度，以秒為單位。 | 媒體關閉 | `a.media.states.`<br>`infocus.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL 受靜音影響的資料流]** | 在播放工作階段期間發生至少一個靜音狀態時觸發。 | 媒體關閉 | `a.media.states.`<br>`mute.set` | `xdm.mediaReporting.`<br>`states.[*].isSet` |
| **[!UICONTROL 靜音計數]** | 視訊進入「靜音」狀態的次數。 | 媒體關閉 | `a.media.states.`<br>`mute.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 靜音總時間]** | 視訊處於靜音狀態的時間長度，以秒為單位。 | 媒體關閉 | `a.media.states.`<br>`mute.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
| **[!UICONTROL 受子母畫面影響的資料流]** | 如果在播放工作階段期間發生至少一個子母畫面狀態，則會觸發。 | 媒體關閉 | `a.media.states.`<br>`pictureinpicture.set` | `mediaReporting.states.`<br>`[*].isSet` |
| **[!UICONTROL 子母畫面計數]** | 視訊進入「子母畫面」狀態的次數。 | 媒體關閉 | `a.media.states.`<br>`pictureinpicture.count` | `xdm.mediaReporting.`<br>`states.[*].count` |
| **[!UICONTROL 子母畫面總時間]** | 視訊處於子母畫面狀態的時間長度（以秒為單位）。 | 媒體關閉 | `a.media.states.`<br>`pictureinpicture.time` | `xdm.mediaReporting.`<br>`states.[*].time` |
