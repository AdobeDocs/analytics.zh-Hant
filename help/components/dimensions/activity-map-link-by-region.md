---
title: Activity Map 連結 (依地區)
description: 連結和區域的串連值。
feature: Dimensions
role: User, Admin
source-git-commit: 65e75a1c2b39823e72abfb0e5b61122c62f1f013
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 11%

---

# Activity Map 連結 (依地區)

「依地區的Activity Map連結」 [維度](overview.md)顯示[Activity Map連結](activity-map-link.md)和[Activity Map地區](activity-map-link-by-region.md)的串連。 如果您的連結名稱類似，但位於網站的不同區域，此維度就十分實用。 例如，如果您有多個首頁的連結全部標示為「首頁」，您可以使用此維度來區分每個網站區域中的這些連結。

## 將資料填入此維度中

此維度會從[內容資料變數](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`和`c.a.activitymap.region`擷取資料。 這兩個值會串連並以縱線符號(`|`)分隔。 如果您的實作使用[Activity Map](/help/analyze/activity-map/overview.md)，這些內容資料變數會在點按連結時自動收集資料。

## 維度項目

Dimension專案包含來自[Activity Map連結](activity-map-link.md)和[Activity Map地區](activity-map-link-by-region.md)的值。 您組織的網站結構和實作會決定收集的確切值。
