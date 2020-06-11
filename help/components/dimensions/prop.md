---
title: Prop
description: 可用於報表的自訂維度。
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 28%

---


# Prop

*此說明頁面說明prop如何以維度運作。 For information on how to implement props, see[props](/help/implement/vars/page-vars/prop.md)in the Implement user guide.*

prop 是自訂變數，您可以視需要使用。它們不會持續存留於設定的點擊以外。

> [!TIP][ Adobe 建議在大部分情況下使用 eVar。](evar.md)在舊版 Adobe Analytics 中，prop 和 eVar 各有其優缺點。不過 Adobe 已改良 eVar，現在它們幾乎能完成 prop 的所有使用案例。

如果您有解決方 [案設計檔案](/help/implement/prepare/solution-design.md)，您可以將這些自訂維度分配給您組織的特定值。 可用的Prop數量視您與Adobe的合約而定。 若您與Adobe的合約支援，最多可使用75個Prop。

## 以資料填入Prop

每個prop會收集影像請求 [`c1` 中- `c75` 查詢字串](/help/implement/validate/query-parameters.md) 的資料。 例如，查詢字 `c1` 串參數會收集prop1的資料，而查詢字串參 `c68` 數則會收集prop68的資料。

AppMeasurement會將JavaScript變數編譯為影像要求以進行資料收集，它會使用變 `prop1` 數- `prop75`。 如需實 [作指引](/help/implement/vars/page-vars/prop.md) ，請參閱實作使用指南中的prop。

## 維度值

由於prop在實作中包含自訂字串，因此您的組織會決定每個prop的維度值。 請務必在解決方案設計檔案中記錄每個prop和典型維 [度值的用途](/help/implement/prepare/solution-design.md)。

## eVar上的prop值

 Adobe 建議在大部分情況下使用 eVar。此語句的例外如下：

* 您可以在即時報表中使用prop。 eVar至少需要30分鐘才能顯示在報表中。
* prop 可成為清單屬性，這些 prop 能在同一次點擊中接受多個值。清單變數是個別的變數，而且只有三個清單變數可供使用。
* 當您對prop啟用路徑分析時，「登入」 [和「退出](entry-dimensions.md) 」維 [](exit-dimensions.md) 度會立即變為可用。 如果您想要eVar的登入和退出維度，可以手動建立區段。

如需 [](evar.md) prop與eVar之間的更多比較，請參閱eVar。
