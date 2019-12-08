---
description: 說明如何使用資料摘要來計算通用量度。
keywords: Data Feed;job;metrics;pre column;post column;bots;date filtering;event string;common;formulas
title: 計算量度
topic: Reports and analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用資料饋送來計算常用量度

說明如何使用資料摘要來計算通用量度。

> [!IMPORTANT] 通常從Adobe Analytics排除的點擊會包含在資料饋送中。 使用 `exclude_hit > 0` 移除原始資料查詢的已排除點擊。 資料來源的資料也包含在資料饋送中。 如果要排除資料來源，請排除所有含有的列 `hit_source = 5,7,8,9`。

## 頁面檢視

1. 計算值位於或中的行 `post_pagename` 數 `post_page_url`。

## 瀏覽

1. 串連 `post_visid_high`、 `post_visid_low`、 `visit_num`和 `visit_start_time_gmt`。
1. 計算唯一值數。

> [!NOTE] 網際網路不規範、系統不規範或使用自訂訪客ID很少會針對不同的瀏覽 `visit_num` 使用相同的值。 計算 `visit_start_time_gmt` 瀏覽次數時使用，以確定已計算這些瀏覽。

## 訪客

Adobe用來識別獨特訪客的所有方法（自訂訪客ID、Experience Cloud ID服務等）的值，這些值都會以和中的 `post_visid_high` 值計算 `post_visid_low`。 這兩欄的串連可用作識別獨特訪客的標準，不論其被識別為獨特訪客的方式為何。 如果您想瞭解Adobe用來識別獨特訪客的方法，請使用欄 `post_visid_type`。

1. 串連 `post_visid_high` 和 `post_visid_low`。
2. 計算唯一值數。

## 自訂、下載或退出連結

1. 計算下列位置的列數：
   * `post_page_event = 100` 自訂連結
   * `post_page_event = 101` 下載連結
   * `post_page_event = 102` 退出連結

## 自訂事件

所有量度都會以逗號 `post_event_list` 分隔的整數計入欄中。 使用 `event.tsv` 來比對數值與所需事件。 例如，指 `post_event_list = 1,200` 出點擊包含購買事件和自訂事件1。

1. Count the number of times the event lookup value appears in `post_event_list`.

## 逗留時間

首先必須依瀏覽來分組點擊，然後根據瀏覽中的點擊數排序。

1. 串連 `post_visid_high`、 `post_visid_low`、 `visit_num`和 `visit_start_time_gmt`。
2. 依此串連值排序，然後依此套用次要排序 `visit_page_num`。
3. 如果點擊不是瀏覽中的最後一個，請從後續 `post_cust_hit_time` 點擊的值中減去該 `post_cust_hit_time` 值。
4. 此數字是點擊逗留的時間（以秒為單位）。 可套用篩選條件，以聚焦維度值或事件。

## 訂單、件數和收入

如果點擊的 `currency` 值不符合報表套裝的貨幣，則會使用當天的兌換率來轉換。 該欄使 `post_product_list` 用轉換的貨幣值，因此所有點擊在此欄中都使用相同的貨幣。

1. Exclude all rows where `duplicate_purchase = 1`.
2. 僅包含包含購 `event_list` 買事件的列。
3. 剖析欄 `post_product_list` 以擷取所有價格資料。 欄的 `post_product_list` 格式與變數的格式 `s.products` 相同。
4. 計算所需量度：
   * 計算要計算訂單的行數
   * 總和產品字 `quantity` 串中的數目以計算單位
   * 總和產品字串 `price` 中的數量以計算收入
