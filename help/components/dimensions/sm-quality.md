---
title: 串流媒體品質維度
description: 為報表套裝啟用[!UICONTROL 媒體品質]時可用的維度。
feature: Dimensions
exl-id: e3794d8c-3c03-425d-850c-a735b579324b
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# 串流媒體品質維度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體品質]時可用的維度。 如需可用的量度，請參閱[串流媒體品品質度](../metrics/sm-quality.md)。*

串流媒體品質維度提供與訪客使用的內容品質相關的報表。 使用這些維度需要[!UICONTROL Adobe串流媒體集合]。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在[媒體報告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下啟用&#x200B;**[!UICONTROL 媒體品質]**&#x200B;時，可以使用下列維度：

| Dimension名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 平均位元速率 | 以100-KBPS貯體間隔表示的平均位元速率。 其計算方式為與指定播放工作階段之播放持續時間相關的所有位元速率值的加權平均。 | 媒體關閉 | `a.media.qoe.bitrateAverageBucket` |
| 位元速率變更 | 錄放工作階段發生的位元速率變更次數。 | 媒體關閉 | `a.media.qoe.bitrateChangeCount` |
| 緩衝事件 | 媒體播放器在播放工作階段期間進入緩衝狀態的次數。 | 媒體關閉 | `a.media.qoe.bufferCount` |
| 總緩衝期間 | 緩衝花費的總時間量（以秒為單位）。 | 媒體關閉 | `a.media.qoe.bufferTime` |
| 掉格 | 錄放工作階段發生的掉格總數。 | 媒體關閉 | `a.media.qoe.droppedFrameCount` |
| 錯誤 | 錄放工作階段發生的錯誤總數。 | 媒體關閉 | `a.media.qoe.errorCount` |
| 外部錯誤ID | 來自任何外部來源的所有唯一錯誤ID，例如CDN錯誤。 您必須提供所需的錯誤代碼或ID。 允許多個錯誤ID。 | 媒體關閉 | `a.media.qoe.externalErrors` |
| 播放器SDK錯誤ID | 內容播放器SDK產生的所有唯一錯誤ID。 您必須提供所需的錯誤代碼或ID。 允許多個錯誤ID。 | 媒體關閉 | `a.media.qoe.playerSdkErrors` |
| 開始時間 | 如果未透過QoSObject設定，則此值預設為`0`。 設定值（以毫秒為單位）。 Analysis Workspace會以秒為單位報告此維度。 | 媒體開始、媒體關閉 | `a.media.qoe.timeToStart` |

{style="table-layout:auto"}
