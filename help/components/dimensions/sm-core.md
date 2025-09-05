---
title: 串流媒體服務核心維度
description: 為報表套裝啟用[!UICONTROL 媒體核心]時可用的維度。
feature: Dimensions
exl-id: 1316a646-a31a-49a4-a670-d56d90dd462b
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 9%

---

# 串流媒體服務核心維度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體核心]時可用的維度。 如需可用的量度，請參閱[串流媒體服務核心量度](../metrics/sm-core.md)。*

串流媒體服務核心維度透過串流媒體服務程式庫收集的資料提供基本報表功能。 使用這些維度需要&#x200B;**[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[媒體核心](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 內容 | 內容的內容ID。 | 媒體開始、媒體關閉 | `a.media.name` |
| 內容管道 | 播放內容的分發站台或頻道。 任何字串值都有效。 | 媒體開始、媒體關閉 | `a.media.channel` |
| 內容長度（變數） | 使用內容的最大長度（或持續時間），以秒為單位。 數個量度需要此維度，包括「平均每分鐘觀眾數」。 如果此維度未設定，將無法使用相依量度。<br><br>也提供名為「視訊長度」的分類維度，其用途類似。 此維度和分類會被視為兩個不同的維度。 | 媒體開始、媒體關閉 | `a.media.length` |
| 內容名稱（變數） | 內容的易記名稱。 名為「影片名稱」的分類也可使用，其用途類似。 此維度和分類會被視為兩個不同的維度。 | 媒體開始、媒體關閉 | `a.media.friendlyName` |
| 內容播放器名稱 | 內容播放器的名稱。 | 媒體開始、媒體關閉 | `a.media.playerName` |
| 內容區段 | 說明已檢視部分內容的間隔（分鐘）。 此區段的計算方式為播放工作階段期間播放點值的最大值與最小值。 | 媒體關閉 | `a.media.segment` |
| 內容類型 | 內容型別。 有效值包括`song`、`podcast`、`audiobook`、`radio`、`VoD`、`Live`、`Linear`、`UGC`、`DVoD`或自訂值。 | 媒體開始、媒體關閉 | `a.contentType` |
| 媒體路徑 | 訪客到達內容所使用的路徑。 | 媒體開始 | `a.media.path` |
| 資料流類型 | 資料流類型。有效值包括 `audio` 和 `video`。 | 媒體開始、媒體關閉 | `a.media.streamType` |

{style="table-layout:auto"}

除了上述維度之外，Adobe會自動建立下列分類維度。 您必須上傳分類資料，才能檢視使用這些維度的報表。

| 分類名稱 | 父維度 | 說明 |
| --- | --- | --- |
| 影片長度 | 內容 | 使用內容的最大長度（或持續時間），以秒為單位。 依賴內容長度的量度無法使用此分類；您必須建立計算量度，以使用此分類來取得「平均每分鐘觀眾數」等量度。 |
| 影片名稱 | 內容 | 內容的易記名稱。 它是內容名稱（變數）的同等分類。 |

{style="table-layout:auto"}
