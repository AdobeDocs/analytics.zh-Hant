---
title: 單頁造訪次數 (量度)
description: 「頁面」維度項目在造訪中未變更的次數。
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 86%

---

# 單頁造訪次數

*此說明頁面說明「單頁造訪次數」作為量度時的運作方式。如需詳細資訊，請參閱[單頁造訪次數](../dimensions/single-page-visits.md)維度。*

[!UICONTROL 單頁造訪次數] [量度](overview.md)會顯示[頁面](../dimensions/page.md)維度專案在整個造訪中僅包含單一不重複值的造訪次數。 當您想要了解短期造訪次數維度，但沒有設定像是[[!UICONTROL 跳出數]](bounces.md)那樣嚴格的規則時，此量度就會很有用。

## 此量度的計算方式

此量度會計算[!UICONTROL 頁面]維度項目在整個造訪期間僅包含單一唯一值的造訪次數。 如果訪客重新載入頁面或引發連結追蹤呼叫，仍會計為單頁造訪次數。當「頁面」維度變更為第二個不重複值時，該次造訪即不再符合單頁造訪的資格。

如需量度之間的比較，請參閱[單次存取](single-access.md)。

## 計算重複實例數

此設定指定是否要將重複實例計入報表中。 如需詳細資訊，請參閱「[計算重複實例數](/help/components/metrics/count-repeat-instances.md)」。
