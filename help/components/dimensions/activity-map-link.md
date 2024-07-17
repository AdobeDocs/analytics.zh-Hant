---
description: 被點按的連結名稱。
title: Activity Map 連結
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 8%

---

# Activity Map 連結

「Activity Map連結」[維度](overview.md)會顯示最常被點按的連結。 您可以使用此維度來比較網站上最常使用哪些連結，無論連結的點按位置為何。

## 將資料填入此維度中

此維度會從[內容資料變數](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`擷取資料。 如果您的實作使用[Activity Map](/help/analyze/activity-map/overview.md)，此內容資料變數會在點按連結時自動收集資料。

對於點按的指定連結，Activity Map會依序搜尋下列專案：

1. `s_objectID`變數
1. 連結的內部文字
1. 影像的`alt`屬性
1. `title`屬性
1. 影像的`src`屬性
1. 表單的`action`屬性

如果點按的元素不包含上述任何條件，Activity Map就不會收集該點按的資料。

## 維度項目

Dimension專案包含訪客點按的連結文字或其他連結屬性。 您組織的網站結構和實作會決定收集的確切值。
