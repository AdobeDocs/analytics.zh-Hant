---
title: 實例
description: 變數經設定 (且不持續存在) 的點擊次數。
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
TQID: https://experienceleague.adobe.com/a6Ycw6CVzeSKuOCHezQtLNIZZo6vbkVneVWO0C2QfxQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 263
ht-degree: 50%

---

# 實例

「執行個體」[量度](overview.md)顯示維度明確定義於影像要求中的次數。 有些維度 (例如 [eVar](../dimensions/evar.md)) 在其設定所在的點擊過後仍會保存維度項目。 如果您想要查看某個維度項目在加以保存的值點擊不存在的情況下進行設定的次數，此量度就十分實用。

## 此量度的計算方式

在報表套裝中的所有點擊中，僅納入在影像要求中明確設定維度項目的點擊。 有些維度 (例如 [eVar](../dimensions/evar.md)) 在其設定所在的點擊過後仍會持續存在。 [頁面檢視](page-views.md)和[發生次數](occurrences.md)之類的量度，會同時計入初始值和持續值。 此量度不會計入持續值。

例如，某個訪客進入您的網站並使用內部搜尋。 您可在eVar1中追蹤內部搜尋。 使用內部搜尋一次後，使用者在離開前會再造訪五個頁面。

在Workspace中檢視報表時，您會看到一個eVar1例項和六次發生次數。 搜尋結果頁面上會計入一個執行個體，而發生次數量度會計入初始值和後續儲存值。

## 與類似量度比較

* **執行個體與[發生次數](occurrences.md)**：執行個體不包含維度專案持續存在的點選。 發生次數會計入維度專案經設定或持續存在的點選。
* **執行個體與[頁面檢視](page-views.md)**&#x200B;的比較：執行個體包含所有點選型別，包括頁面檢視追蹤呼叫([`t()`](/help/implement/vars/functions/t-method.md))、連結追蹤呼叫([`tl()`](/help/implement/vars/functions/tl-method.md))，以及來自摘要[資料來源](/help/import/data-sources/overview.md)的資料。 頁面檢視量度僅包括頁面檢視追蹤呼叫，不包括連結追蹤呼叫和摘要資料來源。
