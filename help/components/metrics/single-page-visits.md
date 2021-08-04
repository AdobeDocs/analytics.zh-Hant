---
title: 單頁造訪次數
description: 「頁面」維度項目在造訪中未變更的次數。
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 98463103e6e2ba19d11629d40dacc0c02f5b33c9
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 57%

---

# 單頁造訪次數

*此說明頁面說明「單頁造訪次數」作為量度時的運作方式。如需詳細資訊，請參閱[單頁造訪次數](../dimensions/single-page-visits.md)維度。*

[!UICONTROL 單頁造訪次數]量度會顯示[頁面](../dimensions/page.md)維度項目在整個造訪中僅包含單一不重複值的造訪次數。 對於某些維度，如果您想要查看短時間造訪，但沒有[[!UICONTROL 跳出數]](bounces.md)那麼嚴格的規則，此量度將有所幫助。

## 此量度的計算方式

此量度會計算[!UICONTROL Page]維度項目在整個造訪中僅包含單一不重複值的造訪次數。 如果訪客重新載入頁面或引發連結追蹤呼叫，仍會計為單頁造訪次數。當「頁面」維度變更為第二個不重複值時，該次造訪即不再符合單頁造訪的資格。

如需量度之間的比較，請參閱[單次存取](single-access.md)。

## 計算重複例項

此設定指定是否要將重複執行個體計入報表。如需詳細資訊，請參閱[計算重複例項](/help/components/metrics/count-repeat-instances.md)。