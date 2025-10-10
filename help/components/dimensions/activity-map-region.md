---
title: Activity Map 地區
description: 您網站上被點按的地區。
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 5%

---

# Activity Map 地區

「Activity Map地區」[維度](overview.md)會顯示網站上點按次數最多的地區。 如果您想比較網站總體區域而非個別連結的點按次數，此維度就十分實用。 此外，對於網站中提供動態內容的區域也很有幫助。 例如，如果您的首頁有旋轉的新聞文章，則很難使用[Activity Map連結](activity-map-link.md)維度，因為連結文字會持續變更。 不過，由於這些連結會使用相同的區域，因此您可以分析該區域效能，即使個別連結可能每天都會變更。

## 將資料填入此維度中

此維度會從[內容資料變數](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`擷取資料。 如果您的實作使用[Activity Map](/help/analyze/activity-map/overview.md)，此內容資料變數會在點按連結時自動收集資料。

對於已點按的指定連結，請檢查下列專案的父DOM元素（依序）：

* 由[`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md)設定的屬性中的值 — 預設設定為`id`屬性
* 屬性`aria-label`時`role="region"`屬性中的值
* 語意元素`<header>`、`<main>`、`<footer>`或`<nav>` (僅限Web SDK)

如果父DOM元素不符合上述任何條件，則會遞回地繼續在DOM階層中搜尋。 如果找不到相符的元素，則會傳回值`BODY`。

## 維度項目

Dimension專案包含您在網站上標示的地區。 特定區域值取決於使用的屬性，以及是否有語意HTML元素。
