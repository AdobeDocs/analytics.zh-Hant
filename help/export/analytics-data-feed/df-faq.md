---
description: 與資料摘要相關的常見問題
keywords: Data Feed;job;pre column;post column;case sensitivity
title: 資料摘要常見問答集
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料摘要常見問答集

與資料摘要相關的常見問題。

## 具有 `post_` 首碼的欄與沒有 `post_` 首碼的欄有何不同?

不含 `post_` 首碼的欄包含的資料與資料收集所收到的資料完全相同。具有 `post_` 首碼的欄則包含處理完成後的值。會造成值變更的原因包括變數的持續沿用、處理規則、VISTA 規則、貨幣轉換或 Adobe 套用的其他伺服器端邏輯。Adobe 建議您盡可能使用 `post_` 版本的欄。

如果欄不含 `post_` 版本 (例如 `visit_num`)，則該欄可視為後置欄。

## 資料摘要是否區分大小寫?

在 Adobe Analytics 中，為了報表呈現目的，大部分的變數都不區分大小寫。舉例來說，「snow」、「Snow」、「SNOW」和「sNow」都是相同的值。資料摘要則會區分大小寫。

如果您在非後置欄和後置欄中看到同一值的不同大小寫變化形 (例如，前置欄中是「snow」，後置欄中是「Snow」)，表示您實作時在網站中同時使用了同一值的大寫和小寫版本。前置欄中的大小寫變化形是在之前傳入並儲存在虛擬 cookie 中，或是與該報表套裝在大約相同的時間處理。