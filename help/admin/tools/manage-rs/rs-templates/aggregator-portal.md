---
description: 定義彙總內容之網站 (如新聞入口網站) 的一般設定。
title: 整合入口網站
feature: Report Suite Settings
exl-id: 48f57f27-289c-4e26-9fb2-e34d48c1f2e6
TQID: https://experienceleague.adobe.com/rH1TSHrMMKxFtMlv0GR-UKF-OJk8SBbt1pq92DYhgVk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 70%

---

# 整合入口網站

定義彙總內容之網站 (如新聞入口網站) 的一般設定。

| 轉換變數 | 類型 | 子關聯 | 配置 | 過期 | `s_code` 變數 |
|---|---|---|---|---|---|
| 內部行銷活動 | 字串 | 基本 | 最近（上一次） | 瀏覽 | `evar1` |
| 內部搜尋詞 | 字串 | 基本 | 最近（上一次） | 瀏覽 | `evar2` |
| 轉介類別 | 字串 | 基本 | 最近（上一次） | 瀏覽 | `evar3` |

| 成功事件 | 類型 | `s_code` 變數 |
|---|---|---|
| 登入 | 計數器（無子關連） | `event1` |
| 推薦檢視 | 計數器（無子關連） | `event2` |
| 反向連結點按次數 | 計數器（無子關連） | `event3` |

| 自訂洞察變數 | `s_code` 變數 |
|---|---|
| 流量屬性 1 - 5 | `prop1, prop2, prop3, prop4, prop5` |

下表包含標準商務事件清單。 這些事件的初始設定在所有報表套裝範本中皆相同。 s_code變數為N/A的事件不需要設定，系統會自動提供。

| 標準Commerce事件 | 類型 | `s_code` 變數 |
|---|---|---|
| 收入 | 計數器 | `purchase` |
| 訂購 | 計數器 | `purchase` |
| 單位數 | 計數器 | `purchase` |
| 購物車 | 計數器 | `scOpen` |
| 購物車檢視 | 計數器 | `scView` |
| 實例 | 計數器 | 不適用 |
| 結帳 | 計數器 | `scCheckout` |
| 購物車新增 | 計數器 | `scAdd` |
| 購物車移除 | 計數器 | `scRemove` |
| 造訪次數 | 計數器（無子關連） | 不適用 |
| 頁面檢視次數 | 計數器（無子關連） | 不適用 |
| 每日不重複訪客 | 計數器（無子關連） | 不適用 |
| 不重複訪客 | 計數器（無子關連） | 不適用 |
