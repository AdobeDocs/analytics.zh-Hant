---
description: 報表 API 的資源和連結。
title: Analytics 報告 API
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: 8f25dfefbc6fba1fb525d2e9e0fce654e21ef362
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 92%

---

# Analytics 報告 API

Adobe AnalyticsAPI的文檔已開啟 [Adobe開發人員](https://developer.adobe.com/analytics-apis/docs/2.0/)。

## Analytics API 的比較

| **API 類型** | **已完整處理** | **即時** | **直播串流** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **說明** | 可在所有 Analytics 介面中使用的完整處理、已完成的資料。 | 收集資料後幾秒鐘內即可使用的部分處理、有限的量度。 | 收集資料後幾秒鐘內即可使用的部分處理的點擊資料。 | 用於提取大型資料匯出的完整處理、已完成的資料。 |
| [**延遲**](/help/technotes/latency.md) | 30-90 分鐘 | 秒 - 10 分鐘 | 秒 - 10 分鐘 | 90+ 分鐘 |
| **處理完成** | 全螢幕 | 部分 | 部分 | 全螢幕 |
| **報告介面** | Analysis Workspace、Reports &amp; Analytics、Report Builder、API | Reports &amp; Analytics、Report Builder、1.4 API 中的即時報表 | 僅 API | Data Warehouse、API |
| **資料詳細程度** | 摘要 | 摘要 | 點擊層級 | 摘要 |
| **訪客資料處理** | 有 | 否 | 否 | 是 |
| **區段支援** | 有 | 否 | 否 | 部分 |
