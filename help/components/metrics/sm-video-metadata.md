---
title: 串流媒體視訊中繼資料量度
description: 當您啟用報表套裝的[!UICONTROL 視訊中繼資料]時可用的量度。
feature: Metrics
exl-id: b2f60a34-e139-4498-bf71-74d291759ef2
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 5%

---

# 串流媒體視訊中繼資料量度

*此頁面說明您為報表套裝啟用[!UICONTROL 視訊中繼資料]時可用的量度。 如需可用的維度，請參閱[串流媒體視訊中繼資料維度](../dimensions/sm-video-metadata.md)。*

串流媒體視訊中繼資料量度透過串流媒體收集程式庫，為資料收集提供補充報告功能。 使用這些量度需要&#x200B;**[!UICONTROL Adobe串流媒體集合]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在[媒體報告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下啟用&#x200B;**[!UICONTROL 視訊中繼資料]**&#x200B;時，可以使用下列量度：

| 量度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 已驗證 | 當使用者透過Adobe驗證獲得授權時觸發的布林值。 | 媒體開始、媒體關閉 | `a.media.pass.auth` |

{style="table-layout:auto"}
