---
description: 定義工作入口網站或職位搜尋網站的一般設定。
title: 工作入口網站
feature: Report Suite Settings
exl-id: d2a03139-7a5d-47bd-a287-fbe83f4a99fd
TQID: https://experienceleague.adobe.com/OVG4imjeOn6ZbW5BzTXVgGvmeNRF8soe1ODrKkIWBVk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 178
ht-degree: 65%

---

# 工作入口網站

定義工作入口網站或職位搜尋網站的一般設定。

| 轉換變數 | 類型 | 子關聯 | 配置 | 過期 | `s_code` 變數 |
|---|---|---|---|---|---|
| 內部行銷活動 | 字串 | 基本 | 最近（上一次） | 瀏覽 | `evar1` |
| 內部搜尋詞 | 字串 | 基本 | 最近（上一次） | 瀏覽 | `evar2` |
| 自助事件型別 | 字串 | 基本 | 最近（上一次） | 瀏覽 | `evar3` |

此報告套裝範本未設定任何成功事件。

| 自訂洞察變數 | `s_code` 變數 |
|---|---|
| 安全/不安全 | `prop1` |
| 流量屬性 2 - 5 | `prop2, prop3, prop4, prop5` |

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
