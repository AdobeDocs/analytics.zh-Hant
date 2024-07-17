---
title: Activity Map 頁面
description: 點按連結時的頁面名稱。
feature: Dimensions
role: User, Admin
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 6%

---

# Activity Map 頁面

「Activity Map頁面」[維度](overview.md)會顯示訪客點按連結時所在的頁面。 您可以使用此維度來判斷哪些頁面包含最常被點按的連結。 Activity Map覆蓋圖也會使用此維度來決定要顯示哪些連結。

## 將資料填入此維度中

此維度會從[內容資料變數](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`擷取資料。 如果您的實作使用[Activity Map](/help/analyze/activity-map/overview.md)，此內容資料變數會在點按連結時自動收集資料。

對於已點按的指定連結，此內容資料變數會收集[頁面](page.md)維度中的值。 如果頁面維度不包含值，則改用[頁面URL](page-url.md)維度（類似於「頁面」維度使用的遞補）。 Activity Map資料通常會在連結被點按後的下一次點選中傳送。 此維度可讓您決定點按連結時的頁面值，而非傳送資料時的頁面值。

## 維度項目

Dimension專案包含在[頁面](page.md)維度中找到的所有值。
