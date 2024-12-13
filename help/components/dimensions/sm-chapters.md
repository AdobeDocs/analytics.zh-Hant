---
title: 串流媒體章節維度
description: 為報表套裝啟用[!UICONTROL 媒體章節]時可用的維度。
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 14%

---

# 串流媒體章節維度

*此頁面說明您為報表套裝啟用[!UICONTROL 媒體章節]時可用的維度。 如需可用的量度，請參閱[串流媒體章節量度](../metrics/sm-chapters.md)。*

串流媒體章節維度透過串流媒體收集程式庫，為資料收集提供補充報告功能。 使用這些維度需要&#x200B;**[!UICONTROL Adobe串流媒體集合]**。 如需詳細資訊，請聯絡您的Adobe客戶團隊。

當您在[媒體報告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md)下啟用&#x200B;**[!UICONTROL 媒體章節]**&#x200B;時，可以使用下列維度：

| 維度名稱 | 說明 | 伴隨傳送 | 上下文資料變數 |
| --- | --- | --- | --- |
| 章節 | 自動產生的章節識別碼。 | 章節關閉 | `a.media.chapter.name` |

{style="table-layout:auto"}

除了上述維度之外，Adobe會自動建立下列分類維度。 您必須上傳分類資料，才能檢視使用這些維度的報表。

| 分類名稱 | 父維度 | 說明 |
| --- | --- | --- |
| 創作者 | [內容](sm-core.md) | 內容的建立者。 |
| 章節長度 | 章節 | 章節長度 (以秒數計)。 |
| 章節名稱 | 章節 | 章節的易記名稱。 |
| 章節位移 | 章節 | 內容內章節從開始的位移（以秒為單位）。 |
| 章節位置 | 章節 | 內容中章節的索引位置。 |

{style="table-layout:auto"}
