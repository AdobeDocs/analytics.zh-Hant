---
description: 用來根據頁面事件判定點擊類型的查詢表。
keywords: 頁面;事件;頁面_事件;張貼_頁面_事件
title: 頁面事件查詢
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 100%

---

# 頁面事件查詢

用來根據 `page_event` 值判定點擊類型的查詢表。如同 [ 資料欄參考](datafeeds-reference.md)所述，`page_event` 與 `post_page_event` 欄位是「tinyint unsigned」。

* 請參閱 [`t()`](/help/implement/vars/functions/t-method.md)，以了解如何為 AppMeasurement 與 Web SDK 實施頁面檢視呼叫。
* 請參閱 [`tl()`](/help/implement/vars/functions/tl-method.md)，以了解如何為 AppMeasurement 與 Web SDK 實施連結追蹤呼叫。
* 請參閱[使用 Adobe Experience Platform Edge Network 實施 Adobe Analytics](/help/implement/aep-edge/overview.md)，以了解 Adobe Analytics 如何將 XDM 承載轉換為頁面事件類型。

| `page_event` 值 | `post_page_event` 值 | 說明 |
| --- | --- | --- |
| `0` | `0` | 所有標準的頁面檢視呼叫。這是大多數點擊的預設值。 |
| `10` | `100` | 自訂連結。將連結類型設為 `o` (AppMeasurement) 或 `xdm.web.webInteraction.type` 至 `other` (Web SDK 或 Mobile SDK)。 |
| `11` | `101` | 下載連結。將連結類型設為 `d` (AppMeasurement) 或 `xdm.web.webInteraction.type` 至 `download` (Web SDK 或 Mobile SDK)。 |
| `12` | `102` | 退出連結。將連結類型設為 `e` (AppMeasurement) 或 `xdm.web.webInteraction.type` 至 `exit` (Web SDK 或 Mobile SDK)。 |
| `31` | `76` | 媒體開始 |
| `32` | `77` | 媒體更新 (不含其他變數處理) |
| `33` | `78` | 媒體更新 (含其他變數處理) |
| `40` | `80` | 調查 |
| `50` | `50` | 串流媒體開始 |
| `51` | `51` | 串流媒體結束 |
| `52` | `52` | 串流媒體進度條拉動 |
| `53` | `53` | 串流媒體保持連線 |
| `54` | `54` | 串流媒體廣告開始 |
| `55` | `55` | 串流媒體廣告結束 |
| `56` | `56` | 串流媒體廣告進度條拉動 |
| `60` | `60` | 黃金時段媒體開始 |
| `61` | `61` | 黃金時段媒體結束 |
| `62` | `62` | 黃金時段媒體進度條拉動 |
| `63` | `63` | 黃金時段媒體保持連線 |
| `64` | `64` | 黃金時段媒體廣告開始 |
| `65` | `65` | 黃金時段媒體廣告結束 |
| `66` | `66` | 黃金時段媒體廣告進度條拉動 |
| `70` | `70` | 包含 Target 活動資料 |
