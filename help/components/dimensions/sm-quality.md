---
title: 串流媒體服務品質維度
description: 為報表套裝啟用[!UICONTROL 媒體品質]時可用的維度。
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 1%

---

# 串流媒體服務品質維度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體品質]時可用的維度。 如需可用的量度，請參閱[串流媒體服務品品質度](../metrics/sm-quality.md)。*

串流媒體服務品質維度提供與訪客使用的內容品質相關的報表。 使用這些維度需要&#x200B;**[!UICONTROL 適用於串流媒體的Adobe Analytics附加元件]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[媒體品質](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 | XDM欄位 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 平均位元速率]** | 以100-KBPS貯體間隔表示的平均位元速率。 其計算方式為與指定播放工作階段之播放持續時間相關的所有位元速率值的加權平均。 | 媒體關閉 | `a.media.qoe.`<br>`bitrateAverageBucket` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrate`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateAverageBucket` |
| **[!UICONTROL 位元速率變更]** | 錄放工作階段發生的位元速率變更次數。 | 媒體關閉 | `a.media.qoe.`<br>`bitrateChangeCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`bitrateChangeCount`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bitrateChangeCount` |
| **[!UICONTROL 緩衝事件]** | 媒體播放器在播放工作階段期間進入緩衝狀態的次數。 | 媒體關閉 | `a.media.qoe.`<br>`bufferCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferCount` |
| **[!UICONTROL 總緩衝期間]** | 緩衝花費的總時間量（以秒為單位）。 | 媒體關閉 | `a.media.qoe.`<br>`bufferTime` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`bufferTime` |
| **[!UICONTROL 掉格]** | 錄放工作階段發生的掉格總數。 | 媒體關閉 | `a.media.qoe.`<br>`droppedFrameCount` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`droppedFrames`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`droppedFrames` |
| **[!UICONTROL 個錯誤]** | 錄放工作階段發生的錯誤總數。 | 媒體關閉 | `a.media.qoe.`<br>`errorCount` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`errorCount` |
| **[!UICONTROL 外部錯誤識別碼]** | 來自任何外部來源的所有唯一錯誤ID，例如CDN錯誤。 您必須提供所需的錯誤代碼或ID。 允許多個錯誤ID。 | 媒體關閉 | `a.media.qoe.`<br>`externalErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`externalErrors` |
| **[!UICONTROL 播放器SDK錯誤ID]** | 內容播放器SDK產生的所有唯一錯誤ID。 您必須提供所需的錯誤代碼或ID。 允許多個錯誤ID。 | 媒體關閉 | `a.media.qoe.`<br>`playerSdkErrors` | `xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`playerSdkErrors` |
| **[!UICONTROL 開始時間]** | 如果未透過QoSObject設定，則此值預設為`0`。 設定值（以毫秒為單位）。 Analysis Workspace會以秒為單位報告此維度。 | 媒體開始、媒體關閉 | `a.media.qoe.`<br>`timeToStart` | `xdm.mediaCollection.`<br>`qoeDataDetails.`<br>`timeToStart`<br><br>`xdm.mediaReporting.`<br>`qoeDataDetails.`<br>`timeToStart` |
