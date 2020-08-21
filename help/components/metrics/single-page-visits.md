---
title: 單頁造訪次數
description: 「頁面」維度項目在瀏覽中未變更的次數。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 62%

---


# 單頁造訪次數

*此說明頁面說明「單頁造訪次數」作為量度時的運作方式。如需詳細資訊，請參閱[單頁造訪次數](../dimensions/single-page-visits.md)維度。*

The &#39;Single page visits&#39; metric shows the number of visits where the [Page](../dimensions/page.md) dimension item contained only a single unique value for the entire visit. 對於某些維度，如果您想要查看短時間造訪，但沒有[跳出數](bounces.md)那麼嚴格的規則，則可以利用此量度。

## 此量度的計算方式

此度量會計算「頁面」維度項目在整個瀏覽中僅包含單一唯一值的瀏覽次數。 如果訪客重新載入頁面或引發連結追蹤呼叫，仍會計為單頁造訪次數。當「頁面」維度變更為第二個不重複值時，該次造訪即不再符合單頁造訪的資格。

如需量度之間的比較，請參閱[單次存取](single-access.md)。
