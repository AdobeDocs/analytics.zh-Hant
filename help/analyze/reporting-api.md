---
description: 報表 API 的資源和連結。
title: Analytics 報告 API
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 90%

---

# Analytics 報告 API

Adobe Analytics API 的相關文件位在 [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/) 上。

## Analytics API 的比較

| **API 類型** | **已完整處理** | **即時** | **直播串流** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **說明** | 可在所有 Analytics 介面中使用的完整處理、已完成的資料。 | 收集資料後幾秒鐘內即可使用的部分處理、有限的量度。 | 收集資料後幾秒鐘內即可使用的部分處理的點擊資料。 | 用於提取大型資料匯出的完整處理、已完成的資料。 |
| [**延遲**](/help/technotes/latency.md) | 30-90 分鐘 | 秒 - 10 分鐘 | 秒 - 10 分鐘 | 90+ 分鐘 |
| **處理完成** | 全螢幕 | 部分 | 部分 | 全螢幕 |
| **報告介面** | Analysis Workspace、Report Builder、API | Report Builder、1.4 API中的即時報表 | 僅 API | Data Warehouse、API |
| **資料詳細程度** | 摘要 | 摘要 | 點擊層級 | 摘要 |
| **訪客資料處理** | 有 | 否 | 否 | 是 |
| **區段支援** | 有 | 否 | 否 | 部分 |
