---
title: 退出維度
description: 列出退出維度及其使用情形。
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 57%

---


# 退出維度

*此說明頁面說明退出作為維度時的運作方式。若要瞭解退出作為量度時的運作方式，請參閱[退出](../metrics/exits.md)量度。*

退出維度會記錄最後一個維度項目，並追溯套用至瀏覽中的所有點擊。 報表套裝設定中的[流量變數](/help/admin/admin/c-traffic-variables/traffic-var.md)下方所有已啟用路徑分析的變數，都可使用退出維度。

## 將資料填入退出維度中

指定的退出維度以其相關聯的流量變數為基礎。如果非退出變數有資料，則其相關聯的退出維度也會包含資料。如果您的流量變數包含資料，即無須對退出維度進行實作變更。

## 維度項目

由於退出變數通常以實作中的自訂字串為基礎，因此您的組織會決定維度項目。 給定退出維中的值與關聯的非退出維中的維項匹配。 例如，「退出頁面」維度中的維度項目在「頁面」維度中包含類似的維度項目。
