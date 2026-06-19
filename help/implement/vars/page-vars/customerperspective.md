---
title: customerPerspect
description: 指定當應用程式於前景或背景時，是否要發生行動應用程式點選。
feature: Appmeasurement Implementation
role: Admin, Developer
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# customerPerspect

`customerPerspective`變數會指定當應用程式於前景或背景時，是否要發生行動應用程式點選。 它會以`cp`查詢引數的形式傳送至Adobe資料集合，並填入[點選型別](/help/components/dimensions/hit-type.md)維度。

## 有效值

`customerPerspective`接受下列字串值：

* `foreground`：點選發生時，應用程式正在使用中。
* `background`：點選發生於應用程式在背景執行時，例如位置更新或由推播通知觸發的點選。

## 此變數的設定方式

Adobe Mobile SDK （4.13.6版及更新版本）會自動設定`customerPerspective`；您通常不會手動設定。 透過AppMeasurement從瀏覽器傳送的點選一律會回報為`foreground`。 如果點選中沒有變數，則會將該點選視為前景點選。

## 對報告的影響

前景/背景區分會影響造訪的處理方式：

* 造訪至少包含一次前景點選時才會計算。
* 背景點選仍可歸因於轉換事件，並可透過虛擬報表套裝中的[內容感知工作階段](/help/components/vrs/vrs-mobile-visit-processing.md)進行分析。 在測量推播通知的有效性時，此行為很有用。
