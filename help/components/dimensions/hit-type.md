---
title: 點擊類型
description: 判斷點擊是前景或背景點擊。
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 34%

---

# 點擊類型

「點選型別」[維度](overview.md)會判斷點選傳送至Adobe資料收集伺服器時，行動應用程式在前景或背景。 此維度僅與包含行動應用程式資料的報表套裝相關。 透過AppMeasurement收集的瀏覽器資料一律會將點選回報為`"Foreground"`。

## 將資料填入此維度中

此維度可立即用於 4.13.6 版或更新版本上的所有行動 SDK 實施作業。 行動SDK會設定[`customerPerspective`](/help/implement/vars/page-vars/customerperspective.md)變數（`cp`查詢引數），以指出每個點選是發生在前景還是背景。 如果您不使用行動SDK，所有點選都會列在`"Foreground"`下。 如果在設定[虛擬報表套裝](../vrs/vrs-mobile-visit-processing.md)時選取&#x200B;**[!UICONTROL 避免背景點選數開始一次新造訪]**，則背景點選數不會使[[!UICONTROL 造訪]](../metrics/visits.md)和[[!UICONTROL 不重複訪客]](../metrics/unique-visitors.md)膨脹。

## 維度項目

維度項目包含 `"Foreground"` 和 `"Background"` 背景點選只會在追蹤的應用程式於背景的行動裝置上發生。
