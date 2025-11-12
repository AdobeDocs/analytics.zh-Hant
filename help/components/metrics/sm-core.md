---
title: 串流媒體服務核心量度
description: 為報表套裝啟用[!UICONTROL 媒體核心]時可用的量度。
feature: Metrics
exl-id: f4ff5f84-18b6-4e67-b808-133faeaf8605
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 2%

---

# 串流媒體服務核心量度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體核心]時可用的量度。 如需可用的維度，請參閱[串流媒體服務核心維度](../dimensions/sm-core.md)。*

串流媒體服務核心量度為透過串流媒體服務收集程式庫收集的資料提供基本報告功能。 使用這些量度需要&#x200B;**[!UICONTROL 適用於串流媒體的Adobe Analytics附加元件]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[媒體核心](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列量度：

| 量度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 | XDM欄位 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 平均分鐘觀眾數]** | 指定內容花費的總時間除以所有播放工作階段的長度。<br>`[Time spent] / [Media length]` | 媒體關閉 | `a.media.`<br>`averageMinuteAudience` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`averageMinuteAudience` |
| **[!UICONTROL 內容完成]** | 內容片段完成時觸發。 此量度並不一定表示他們檢視了整個內容；他們可以略過前面。 這僅表示內容已到達內容的結尾。 | | `a.media.complete` | `xdm.mediaReporting.`<br>`sessionDetails.isCompleted` |
| **[!UICONTROL 已暫停受影響的資料流]** | 如果在內容播放期間發生一或多次暫停即觸發的布林值。 | 媒體關閉 | `a.media.pause` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasPauseImpactedStreams` |
| **[!UICONTROL 暫停事件]** | 錄放工作階段發生的暫停次數。 | 媒體關閉 | `a.media.pauseCount` | `xdm.mediaReporting.`<br>`sessionDetails.pauseCount` |
| **[!UICONTROL 總暫停期間]** | 所有暫停事件的總持續時間（秒）。 | 媒體關閉 | `a.media.pauseTime` | `xdm.mediaReporting.`<br>`sessionDetails.pauseTime` |
| **[!UICONTROL 內容開始]** | 使用媒體的第一個時間格。 如果使用者在廣告期間或緩衝期間中斷，則不會觸發此事件。 | 媒體關閉 | `a.media.play` | `xdm.mediaReporting.`<br>`sessionDetails.isPlayed` |
| **[!UICONTROL 10%進度標籤]**<br>**[!UICONTROL 25%進度標籤]**<br>**[!UICONTROL 50%進度標籤]**<br>**[!UICONTROL 75%進度標籤]**<br>**[!UICONTROL 95%進度標籤]** | 根據長度，播放點超過內容的指定標籤。 每個標籤只會計算1次，即使回頭搜尋也不會重複計入。 如果往前搜尋，跳過的標籤不會計入。 | 媒體關閉 | `a.media.progress10`<br>`a.media.progress25`<br>`a.media.progress50`<br>`a.media.progress75`<br>`a.media.progress95` | `xdm.mediaReporting.`<br>`sessionDetails.hasProgress10`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress25`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress50`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress75`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasProgress95` |
| **[!UICONTROL 內容繼續]** | 在超過30分鐘的緩衝、暫停或延遲期間後繼續播放內容時觸發的布林值。 如果播放器在VideoInfo trackPlay上設定，也會觸發。 | 媒體關閉 | `a.media.resume` | `xdm.mediaCollection.`<br>`sessionDetails.hasResume`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.hasResume` |
| **[!UICONTROL 內容區段檢視]** | 在已檢視區段的第一個影格上觸發的布林值。 | 媒體關閉 | `a.media.segmentView` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`hasSegmentView` |
| **[!UICONTROL 媒體開始]** | 媒體最初載入時觸發的布林值。 此事件包含廣告、緩衝和錯誤。 | 媒體開始 | `a.media.view` | `xdm.mediaReporting.`<br>`sessionDetails.isViewed` |
| **[!UICONTROL 內容逗留時間]** | 主要內容中屬於「播放」型別之所有事件的總事件持續時間（以秒為單位）。 | 媒體關閉 | `a.media.timePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.timePlayed` |
| **[!UICONTROL 不重複播放時間]** | 播放不重複內容的總時間，以秒為單位。 此量度不包括檢視重複內容時的播放時間，例如回頭搜尋。 | 媒體關閉 | `a.media.`<br>`uniqueTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.`<br>`uniqueTimePlayed` |
