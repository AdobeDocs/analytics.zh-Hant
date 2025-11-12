---
title: 串流媒體服務核心維度
description: 為報表套裝啟用[!UICONTROL 媒體核心]時可用的維度。
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 7%

---

# 串流媒體服務核心維度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體核心]時可用的維度。 如需可用的量度，請參閱[串流媒體服務核心量度](../metrics/sm-core.md)。*

串流媒體服務核心維度透過串流媒體服務程式庫收集的資料提供基本報表功能。 使用這些維度需要&#x200B;**[!UICONTROL 適用於串流媒體的Adobe Analytics附加元件]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[媒體核心](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 | XDM欄位 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 內容]** | 內容的內容ID。 | 媒體開始、媒體關閉 | `a.media.`<br>`name` | `xdm.mediaCollection.`<br>`sessionDetails.name`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.name` |
| **[!UICONTROL 內容頻道]** | 播放內容的分發站台或頻道。 任何字串值都有效。 | 媒體開始、媒體關閉 | `a.media.`<br>`channel` | `xdm.mediaCollection.`<br>`sessionDetails.channel`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.channel` |
| **[!UICONTROL 內容長度（變數）]** | 使用內容的最大長度（或持續時間），以秒為單位。 數個量度需要此維度，包括&#39;[!UICONTROL 平均每分鐘觀眾數]&#39;。 如果此維度未設定，將無法使用相依量度。<br><br>也提供名為&#39;[!UICONTROL 視訊長度]&#39;的分類維度，其目的類似。 此維度和分類會被視為兩個不同的維度。 | 媒體開始、媒體關閉 | `a.media.`<br>`length` | `xdm.mediaCollection.`<br>`sessionDetails.length`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.length` |
| **[!UICONTROL 內容名稱（變數）]** | 內容的易記名稱。 也提供名為&#39;[!UICONTROL 視訊名稱]&#39;的分類，其目的類似。 此維度和分類會被視為兩個不同的維度。 | 媒體開始、媒體關閉 | `a.media.`<br>`friendlyName` | `xdm.mediaCollection.`<br>`sessionDetails.friendlyName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.friendlyName` |
| **[!UICONTROL 內容播放器名稱]** | 內容播放器的名稱。 | 媒體開始、媒體關閉 | `a.media.`<br>`playerName` | `xdm.mediaCollection.`<br>`sessionDetails.playerName`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.playerName` |
| **[!UICONTROL 內容區段]** | 說明已檢視部分內容的間隔（分鐘）。 此區段的計算方式為播放工作階段期間播放點值的最大值與最小值。 | 媒體關閉 | `a.media.`<br>`segment` | `xdm.mediaReporting.`<br>`sessionDetails.segment` |
| **[!UICONTROL 內容型別]** | 內容型別。 有效值包括`song`、`podcast`、`audiobook`、`radio`、`VoD`、`Live`、`Linear`、`UGC`、`DVoD`或自訂值。 | 媒體開始、媒體關閉 | `a.contentType` | `xdm.mediaCollection.`<br>`sessionDetails.contentType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.contentType` |
| **[!UICONTROL 媒體路徑]** | 訪客到達內容所使用的路徑。 | 媒體開始 | `a.media.path` | |
| **[!UICONTROL 資料流型別]** | 資料流型別。 有效值包括 `audio` 和 `video`。 | 媒體開始、媒體關閉 | `a.media.`<br>`streamType` | `xdm.mediaCollection.`<br>`sessionDetails.streamType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.streamType` |

除了上述維度之外，Adobe會自動建立下列分類維度。 您必須上傳分類資料，才能檢視使用這些維度的報表。

| 分類名稱 | 父維度 | 說明 |
| --- | --- | --- |
| **[!UICONTROL 視訊長度]** | [!UICONTROL 內容] | 使用內容的最大長度（或持續時間），以秒為單位。 相依於內容長度的量度無法使用此分類；您必須建立計算量度，才能使用此分類取得&#39;[!UICONTROL 平均每分鐘觀眾數]&#39;等量度。 |
| **[!UICONTROL 視訊名稱]** | [!UICONTROL 內容] | 內容的易記名稱。 它等同於&#39;[!UICONTROL 內容名稱（變數）]&#39;的分類。 |
