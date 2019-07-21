---
description: 根據裝置是否啟用或停用 JavaScript，或是計算為「無法辨識」而顯示量度。
seo-description: 根據裝置是否啟用或停用 JavaScript，或是計算為「無法辨識」而顯示量度。
seo-title: JavaScript 支援
solution: Analytics
title: JavaScript 支援
topic: 報表
uuid: 7b95001a-cd35-478a-8b24-54d3066110 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# JavaScript 支援

根據裝置是否啟用或停用 JavaScript，或是計算為「無法辨識」而顯示量度。

>[!NOTE]
>
>In early November 2016, we plan to remove the restriction where JavaScript is always listed as *`disabled / unidentified`* for Mobile devices.

JavaScript 報表對應至原始資料中的欄 javascript。

javascript 是造訪層級欄位，因此可保存造訪中首次點擊的值。欄 javascript 是以 j_jscript 欄中的第一個值為基礎 (例如 visit_referrer 只會保存造訪的第一個反向連結)。

j_jscript 則從 Adobe Analytics 影像請求的參數 j 填入。

其範例如下:

| 點擊 | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

因此，是否在造訪的某個點指定 javascript 版本並不重要，因為首次點擊不包含 j_jscript 的任何值，所以一律會顯示為非 Javascript。
