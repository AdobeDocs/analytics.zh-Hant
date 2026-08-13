---
title: Activity Map 頁面
description: 點按連結時的頁面名稱。
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
TQID: https://experienceleague.adobe.com/WJ0uk-LqIABwehzzy79c2o1cd3EvI-AKUJ--vmLnKRE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 6%

---

# Activity Map 頁面

「Activity Map頁面」[維度](overview.md)會顯示訪客點按連結時所在的頁面。 您可以使用此維度來判斷哪些頁面包含最常被點按的連結。 Activity Map覆蓋圖也會使用此維度來決定要顯示哪些連結。

## 將資料填入此維度中

此維度會從[內容資料變數](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`擷取資料。 如果您的實作使用[Activity Map](/help/analyze/activity-map/overview.md)，此內容資料變數會在點按連結時自動收集資料。

對於已點按的指定連結，此內容資料變數會收集[頁面](page.md)維度中的值。 如果頁面維度不包含值，則改用[頁面URL](page-url.md)維度（類似於「頁面」維度使用的遞補）。 Activity Map資料通常會在連結被點按後的下一次點選中傳送。 此維度可讓您決定點按連結時的頁面值，而非傳送資料時的頁面值。

## 維度項目

Dimension專案包含在[頁面](page.md)維度中找到的所有值。
