---
description: 前置欄包含傳送給資料收集的資料。後置欄包含處理後的值。
keywords: 資料饋送；工作；前置欄；後置欄；大小寫區分
seo-description: 前置欄包含傳送給資料收集的資料。後置欄包含處理後的值。
seo-title: 前置欄和後置欄
solution: Analytics
title: 前置欄和後置欄
topic: Reports & Analytics
uuid: a415327b-6151-4d08-b8 b9-5ab2348 eb0 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 前置欄和後置欄

前置欄包含傳送給資料收集的資料。後置欄包含處理後的值。

例如，變數永續性、處理規則、VISTA 規則和貨幣轉換可能會改變後置欄中顯示之變數所記錄的最終值。除非您要套用自訂的業務邏輯 (例如套用判斷歸因的自訂公式)，否則針對大部分計算請使用後置欄。

如果某欄不含前置或後置版本 (例如 `visit_num`)，則該欄可視為後置欄。Columns prefixed with " `pre_`" typically contain data that was populated by Adobe and not sent by your implementation. For example, `pre_browser` is populated by Adobe, but `evar1` is populated by your implementation. Both of these columns have a " `post_`" column ( `post_browser`, `post_evar1`), which contains the value used by reporting.

## 值的大小寫區分 {#section_F979E099BFAB4AFEBEA2D7E228963CE8}

為了報告的緣故，大部分 Analytics 變數不區分大小寫，也就是說不同的大小寫變化形皆被視為相同的值 ("snow"、"Snow"、"SNOW"、"sNow" 都是同一個值)。不過，基於顯示目的，仍然保留大小寫的區分，因為大多數客戶偏好能夠傳送大小寫混合的字元並顯示在報告之中。

在處理資料饋送時，您可以使用小寫值以利比較，但為了顯示您可能會想保留大小寫。

如果您在前置和後置欄中看到同一值的不同大小寫變化形 (例如，前置欄中是 "snow"，後置欄中是 "Snow")，表示您在網站中同時使用了同一值的大寫和小寫版本。前置欄中的大小寫變化形是在之前傳入並儲存在虛擬 cookie 中，或是與該報表套裝在大約相同的時間處理。例如:

Hit 1: s.list1="Tabby,Persian,Siamese”;

Hit 2: s.list1=“tabby,persian,siamese”;

資料饋送報告 Hit 2 時，前置欄將包含與傳入值大小寫完全相同的值 (tabby,persian,siamese)，但來自 Hit 1 的值可能在該次瀏覽時存續，並在後置欄中報告 (即 Tabby,Persian,Siamese)，因為當執行大小寫無區分的比較時，Hit 1 和 Hit 2 包含完全相同的值。
