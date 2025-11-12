---
title: 串流媒體服務品品質度
description: 為報表套裝啟用[!UICONTROL 媒體品質]時可用的量度。
feature: Metrics
exl-id: a64829b5-d45b-44c6-80c3-5acf1a6d9919
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# 串流媒體服務品品質度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體品質]時可用的量度。 如需可用的維度，請參閱[串流媒體服務品質維度](../dimensions/sm-quality.md)。*

串流媒體服務品品質度透過串流媒體服務程式庫，為資料收集提供補充報告功能。 使用這些量度需要&#x200B;**[!UICONTROL 適用於串流媒體的Adobe Analytics附加元件]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[媒體品質](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列量度：

| 量度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 | XDM欄位 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 平均位元速率]** | 播放工作階段播放期間所有位元速率值的加權平均值。 | 媒體關閉 | `a.media.qoe.`<br>`bitrateAverage` | `xdm.mediaReporting.`<br>`qoeDataDetails.bitrateAverage` |
| **[!UICONTROL 位元速率變更影響的資料流]** | 在播放工作階段期間，如果位元速率至少變更一次，就會觸發的布林值。 | 媒體關閉 | `a.media.qoe.`<br>`bitrateChange` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBitrateChangeImpactedStreams` |
| **[!UICONTROL 位元速率變更]** | 位元速率變更的次數。 | 媒體關閉 | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL 緩衝影響的資料流]** | 如果影片至少進入一次緩衝狀態，便會觸發此布林值。 | 媒體關閉 | `a.media.qoe.`<br>`buffer` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasBufferImpactedStreams` |
| **[!UICONTROL 緩衝事件]** | 錄放工作階段期間影片緩衝的次數。 | 媒體關閉 | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferCount` |
| **[!UICONTROL 總緩衝期間]** | 視訊在所有緩衝事件中花費在緩衝的時間量（以秒為單位）。 | 媒體關閉 | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.bufferTime` |
| **[!UICONTROL 開始前掉格]** | 布林值，若使用者在視訊的主要內容開始之前退出，就會觸發。 | 媒體關閉 | `a.media.qoe.`<br>`dropBeforeStart` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`isDroppedBeforeStart` |
| **[!UICONTROL 掉格]** | 整數，代表播放工作階段期間捨棄的影格總數。 | 媒體關閉 | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.droppedFrames` |
| **[!UICONTROL 掉格影響的資料流]** | 在播放工作階段期間捨棄任何影格時觸發的布林值。 | 媒體關閉 | `a.media.qoe.`<br>`droppedFrames` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasDroppedFrameImpactedStreams` |
| **[!UICONTROL 錯誤影響的資料流]** | 布林值，在播放工作階段期間的任何時間視訊遇到錯誤時觸發。 | 媒體關閉 | `a.media.qoe.`<br>`error` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`hasErrorImpactedStreams` |
| **[!UICONTROL 錯誤事件]** | 整數，代表在播放工作階段期間遇到的錯誤總數。 | 媒體關閉 | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.errorCount` |
| **[!UICONTROL 開始時間]** | 啟動視訊所需的時間（毫秒）。 Adobe會以秒為單位轉換及儲存此值。 | 媒體關閉 | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.timeToStart` |
