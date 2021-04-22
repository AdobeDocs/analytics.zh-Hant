---
title: 單頁造訪次數
description: 「頁面」維度項目在造訪中未變更的次數。
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '166'
ht-degree: 100%

---

# 單頁造訪次數

*此說明頁面說明「單頁造訪次數」作為量度時的運作方式。如需詳細資訊，請參閱[單頁造訪次數](../dimensions/single-page-visits.md)維度。*

「單頁造訪次數」量度會顯示[「頁面」](../dimensions/page.md)維度項目在整個造訪中僅包含單一不重複值的造訪次數。對於某些維度，如果您想要查看短時間造訪，但沒有[跳出數](bounces.md)那麼嚴格的規則，則可以利用此量度。

## 此量度的計算方式

此量度會計算「頁面」維度項目在整個造訪中僅包含單一不重複值的造訪次數。如果訪客重新載入頁面或引發連結追蹤呼叫，仍會計為單頁造訪次數。當「頁面」維度變更為第二個不重複值時，該次造訪即不再符合單頁造訪的資格。

如需量度之間的比較，請參閱[單次存取](single-access.md)。
