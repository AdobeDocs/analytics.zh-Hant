---
description: 有關資料饋送的常見問題
keywords: Data Feed;job;pre column;post column;case sensitivity
title: 資料饋送常見問答集
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料饋送常見問答集

資料饋送的常見問題。

## 前置詞的欄與前置詞的欄 `post_` 有何不 `post_` 同？

不含首碼 `post_` 的欄包含的資料與傳送至資料收集的資料完全相同。 前置詞的 `post_` 欄包含處理後的值。 可變更值的範例包括變數永續性、處理規則、VISTA規則、貨幣轉換或Adobe套用的其他伺服器端邏輯。 Adobe建議盡可能 `post_` 使用欄的版本。

If a column does not contain a `post_` version (for example, `visit_num`), then the column can be considered a post column.

## 資料饋送如何處理區分大小寫？

在Adobe Analytics中，大部分的變數都會被視為不區分大小寫，以利報告。 例如，'snow'、'Snow'、'SNOW'和'sNow'都被視為相同的值。 資料饋送會保留區分大小寫。

如果您在非貼文和貼文欄之間看到相同值的不同大小寫變化（例如，前置欄中為'snow'，後置欄中為'Snow'），則您的實作會在您的網站上同時使用大寫和小寫值。 前置欄中的大小寫變化形是在之前傳入並儲存在虛擬 cookie 中，或是與該報表套裝在大約相同的時間處理。