---
title: 頁面變數
description: 在個別頁面上設定值。
feature: Appmeasurement Implementation
exl-id: 321d0db2-61a3-478e-ab51-8e06c7b2bb7b
role: Admin, Developer
TQID: https://experienceleague.adobe.com/mWfMumcPTklFPKUiGIOatDbC0WKW5RDYH56rXTFk3ZY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 47%

---

# 頁面變數概觀

頁面變數會決定報表中維度和量度的值。

以下清單為實施中常用的變數：

* [`pageName`](pagename.md)：頁面名稱。
* [`campaign`](campaign.md)：將此變數設為促銷活動追蹤的查詢字串參數。
* [`events`](events/events-overview.md)：填入量度以用於報表中。
* [`products`](products.md)：如果您有電子商務網站，請在訪客檢視或購買產品時設定此變數。

## 已淘汰的頁面變數

下列頁面變數已淘汰。 如果您在舊版實作中遇到這些錯誤，請參考這裡檔案。

* **`hier`**：已實作階層變數(`hier1`-`hier5`)以擷取網站的結構以進行報告。 此維度已遭到淘汰，在Analysis Workspace中不是可用維度。 請改用[eVar](evar.md)和分類。
* **`state`**：擷取訪客通常透過送貨或帳單表單進入的美國州。 請改用[[!UICONTROL 美國州]](/help/components/dimensions/us-states.md)維度，Adobe會自動從訪客的地理位置填入該維度。
