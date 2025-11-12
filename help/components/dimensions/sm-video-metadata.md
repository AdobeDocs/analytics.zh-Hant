---
title: 串流媒體服務視訊中繼資料維度
description: 為報表套裝啟用[!UICONTROL 視訊中繼資料]時可用的維度。
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 2%

---

# 串流媒體服務視訊中繼資料維度

*此頁面說明您為報表套裝啟用[!UICONTROL 視訊中繼資料]時可用的維度。 如需可用的量度，請參閱[串流媒體服務視訊中繼資料量度](../metrics/sm-video-metadata.md)。*

串流媒體服務和維度透過串流媒體服務收集程式庫，為資料收集提供補充報告功能。 使用這些維度需要&#x200B;**[!UICONTROL 適用於串流媒體的Adobe Analytics附加元件]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報告]**&#x200B;下啟用[視訊中繼資料](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 | XDM欄位 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 個廣告載入]** | 已載入的廣告型別。 | | `a.media.adLoad` | `xdm.mediaCollection.`<br>`sessionDetails.adLoad` |
| **[!UICONTROL 天部分]** | 內容播出或播放的當天時間。 支援任何字串值。 | 媒體開始、媒體關閉 | `a.media.dayPart` | `xdm.mediaCollection.`<br>`sessionDetails.dayPart`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.dayPart` |
| **[!UICONTROL 集]** | 集數。 | 媒體開始、媒體關閉 | `a.media.episode` | `xdm.mediaCollection.`<br>`sessionDetails.episode`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.episode` |
| **[!UICONTROL 媒體摘要型別]** | 摘要型別。 | 媒體開始、媒體關閉 | `a.media.feed` | `xdm.mediaCollection.`<br>`sessionDetails.feed`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.feed` |
| **[!UICONTROL 型別]** | 內容製作者定義的內容型別或群組。 此維度支援多個值，並以逗號分隔。 | 媒體開始、媒體關閉 | `a.media.genre` | `xdm.mediaCollection.`<br>`sessionDetails.genre`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.genreList` |
| **[!UICONTROL MVPD]** | Adobe驗證提供的MVPD。 | 媒體開始、媒體關閉 | `a.media.pass.mvpd` | `xdm.mediaCollection.`<br>`sessionDetails.mvpd`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.mvpd` |
| **[!UICONTROL 網路]** | 網路或頻道名稱。 | 媒體開始、媒體關閉 | `a.media.network` | `xdm.mediaCollection.`<br>`sessionDetails.network`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.network` |
| **[!UICONTROL 季]** | 此演出節目所屬的季數。 | 媒體開始、媒體關閉 | `a.media.season` | `xdm.mediaCollection.`<br>`sessionDetails.season`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.season` |
| **[!UICONTROL 節目]** | 節目或影集名稱。 | 媒體開始、媒體關閉 | `a.media.show` | `xdm.mediaCollection.`<br>`sessionDetails.show`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.show` |
| **[!UICONTROL 顯示型別]** | 代表內容型別的整數。<br>`0`：全集<br>`1`：預覽或預告<br>`2`：片段<br>`3`：其他 | 媒體開始、媒體關閉 | `a.media.type` | `xdm.mediaCollection.`<br>`sessionDetails.showType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.showType` |

