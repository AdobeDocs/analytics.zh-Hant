---
description: 說明如何使用資料摘要來計算通用量度。
keywords: 資料摘要；量度；預先欄位；後置欄位；bots；日期篩選器；事件字串；一般；公式
title: 計算量度
feature: Data Feeds
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
source-git-commit: adee2f1013cfd2ae231e3133b5a5327b8792bd16
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 100%

---

# 使用資料摘要來計算常用量度

說明如何使用資料摘要來計算通用量度。

>[!NOTE]
>
>通常從 Analysis Workspace 排除的點擊會包含在資料摘要中。如果相關，請考慮在查詢中加入以下條件：
>
>* **`exclude_hit`**：Analysis Workspace 僅包含符合 `exclude_hit = 0` 條件的資料。
>* **`customer_perspective`**：Analysis Workspace 僅包含符合 `customer_perspective = 0` 條件的資料，除非您使用包含行動背景點擊的虛擬報告套裝。
>* **`hit_source`**：來自資料來源的資料在原始資料和 Analysis Workspace 之間可能存在差異。如果您想要排除來自資料來源的點擊，請排除符合 `hit_source = 5,7,8,9` 條件的所有列。

## 頁面檢視

1. 計算 `post_pagename` 或 `post_page_url` 中有值的列數。

## 發生次數

1. 計算總列數。

## 造訪次數

1. 串連 `post_visid_high`、`post_visid_low`、`visit_num` 和 `visit_start_time_gmt`。
1. 計算值的唯一數目。

>[!TIP]
>
>網際網路違規、系統不正確或使用自訂訪客 ID，可能會在極少數情況中針對不同的瀏覽使用相同的 `visit_num` 值。雖然是選擇性的，但在計算造訪次數時請使用 `visit_start_time_gmt`，以確保這些造訪次數被納入計算。

## 訪客

Adobe 用來識別不重複訪客的所有方法 (自訂訪客 ID、Experience Cloud ID 服務等) 最終都會計算為 `post_visid_high` 和 `post_visid_low` 中的一個值。這兩欄的串連可用來當作識別獨特訪客的標準，不論識別為獨特訪客的方式為何皆然。如果您想了解 Adobe 用來識別獨特訪客的方法，請使用 `post_visid_type` 欄。

1. 串連 `post_visid_high` 和 `post_visid_low`。
2. 計算值的唯一數目。

## 自訂、下載或退出連結

1. 計算下列位置的列數：
   * 自訂連結使用 `post_page_event = 100`
   * 下載連結使用 `post_page_event = 101`
   * 退出連結使用 `post_page_event = 102`

## 自訂事件

在 `post_event_list` 欄中，所有量度都會以逗號分隔的整數計算。使用 `event.tsv` 來比對數值與所需事件。例如，`post_event_list = 1,200` 表示點擊包含購買事件和自訂事件 1。

1. 計算 `post_event_list` 中出現的事件查閱值次數。

## 逗留時間

首先必須依瀏覽來分組點擊，然後根據瀏覽中的點擊數排序。

1. 串連 `post_visid_high`、`post_visid_low`、`visit_num` 和 `visit_start_time_gmt`。
2. 依此串連值排序，然後依 `visit_page_num` 套用次要排序。
3. 如果點擊不是瀏覽中的最後一個，請從後續點擊的 `post_cust_hit_time` 值中減去該 `post_cust_hit_time` 值。
4. 此數字是點擊的逗留時間 (以秒為單位)。可套用篩選條件，以著重在維度項目或事件。

## 訂購、件數和收入

如果點擊的 `currency` 值不符合報告套裝的貨幣，則會使用當天的匯率來轉換。`post_product_list` 欄使用轉換的幣值，因此此欄中的所有點擊都使用相同的貨幣。

1. 排除 `duplicate_purchase = 1` 的所有行。
2. 僅包含 `event_list` 包含購買事件的列。
3. 剖析 `post_product_list` 欄以擷取所有價格資料。`post_product_list` 欄的格式與 `s.products` 變數的格式相同。
4. 計算所需量度：
   * 計算列數來計算訂購數
   * 加總產品字串中的 `quantity` 數目以計算件數
   * 加總產品字串中的 `price` 數目以計算收入
