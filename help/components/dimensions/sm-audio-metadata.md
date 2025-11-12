---
title: 串流媒體服務音訊中繼資料維度
description: 為報表套裝啟用[!UICONTROL 音訊中繼資料]時可用的維度。
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 4%

---

# 串流媒體服務音訊中繼資料維度

串流媒體服務和維度透過串流媒體服務程式庫，為資料收集提供補充報表功能。 使用這些維度需要&#x200B;**[!UICONTROL 適用於串流媒體的Adobe Analytics附加元件]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在&#x200B;**[!UICONTROL 媒體報表]**&#x200B;下啟用[音訊中繼資料](/help/admin/tools/manage-rs/edit-settings/media-management.md)時，可以使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 | XDM欄位 |
| --- | --- | --- | --- | --- |
| **[!UICONTROL 相簿]** | 相簿的名稱。 | 媒體開始、媒體關閉 | `a.media.album` | `xdm.mediaCollection.`<br>`sessionDetails.album`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.album` |
| **[!UICONTROL 藝人]** | 藝人的姓名。 | 媒體開始、媒體關閉 | `a.media.artist` | `xdm.mediaCollection.`<br>`sessionDetails.artist`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.artist` |
| **[!UICONTROL 作者]** | 有聲書作者的姓名。 | 媒體開始、媒體關閉 | `a.media.author` | `xdm.mediaCollection.`<br>`sessionDetails.author`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.author` |
| **[!UICONTROL Label]** | 紀錄標籤的名稱。 | 媒體開始、媒體關閉 | `a.media.label` | `xdm.mediaCollection.`<br>`sessionDetails.label`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.label` |
| **[!UICONTROL 發行者]** | 音訊內容發行者的名稱。 | 媒體開始、媒體關閉 | `a.media.publisher` | `xdm.mediaCollection.`<br>`sessionDetails.publisher`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.publisher` |
| **[!UICONTROL 電台]** | 廣播電台的名稱或ID。 | 媒體開始、媒體關閉 | `a.media.station` | `xdm.mediaCollection.`<br>`sessionDetails.station`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.station` |
