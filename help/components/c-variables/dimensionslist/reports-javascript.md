---
description: 根據裝置是否啟用或停用 JavaScript，或是計算為「無法辨識」而顯示量度。
title: JavaScript 支援
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# JavaScript 支援

根據裝置是否啟用或停用 JavaScript，或是計算為「無法辨識」而顯示量度。

>[!NOTE] 在 2016 年 11 月初，我們計劃移除行動裝置上 JavaScript 一律被列為 *`disabled / unidentified`* 的限制。

JavaScript報表會對應原始資料中的欄javascript。

javascript是瀏覽層級欄位，因此會保留瀏覽中首次點擊的值。 欄javascript是以j_jscript欄中出現的第一個值為基礎（如visit_referrer只會保留瀏覽的第一個反向連結）。

j_jscript會從Adobe Analytics影像要求的參數j填入。

其範例如下：

| 點擊 | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

因此，您是否在瀏覽中的某個時點指定javascript版本並不重要，因為第一次點擊不包含j_jscript的任何值，所以一律會顯示為非Javascript。
