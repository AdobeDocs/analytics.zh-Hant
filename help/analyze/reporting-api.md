---
description: 報表 API 的資源和連結。
title: Analytics 報告 API
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: a9d892ab8caaeb797fbbd9b5aa136c5dab76f8bd
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 73%

---

# Analytics 報告 API

Adobe Analytics API的檔案位於[Adobe I/O](https://adobe.io/analytics-apis/docs)。

## Analytics API比較

| **API 類型** | **完整處理** | **即時** | **直播串流** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **說明** | 可在所有 Analytics 介面中使用的完整處理、已完成的資料。 | 收集資料後幾秒鐘內即可使用的部份處理、有限的量度。 | 收集資料後幾秒鐘內即可使用的部份處理的點擊資料。 | 用於提取大型資料匯出的完整處理、已完成的資料。 |
| [**延遲性**](/help/technotes/latency.md) | 30-90 分鐘 | 秒 -10 分鐘 | 秒 -10 分鐘 | 90分鐘以上 |
| **處理完成** | 全螢幕 | 部份 | 部份 | 全螢幕 |
| **報告介面** | Analysis Workspace、Reports &amp; Analytics、Report Builder、API | Reports &amp; Analytics、Report Builder、1.4 API中的即時報表 | 僅 API | Data Warehouse, API |
| **資料粒度** | 摘要 | 摘要 | 點擊層級 | 摘要 |
| **訪客設定檔處理** | 有 | 否 | 否 | 是 |
| **區段支援** | 有 | 否 | 否 | 部份 |
