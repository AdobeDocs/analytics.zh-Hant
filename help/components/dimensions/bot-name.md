---
title: 機器人名稱
description: 符合機器人規則的機器人名稱。
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
TQID: https://experienceleague.adobe.com/lJn65s1JtcJf7WobPEeouvwlk7G5qd8XtgxvGLY-zu8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 7%

---

# 機器人名稱

「機器人名稱」 [維度](overview.md)顯示使用[機器人規則](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)偵測到的機器人名稱。 這些規則可以是預設IAB規則，或貴組織設定的自訂機器人規則。 若您想進一步瞭解哪些機器人正在造訪您的網站，或哪些機器人產生最多流量，則此功能會很有幫助。

系統會自動從所有的Analytics報表中篩選符合[!UICONTROL 機器人規則]的點選，但此維度、[機器人發生次數](../metrics/bot-occurrences.md)和[機器人頁面檢視次數](../metrics/bot-page-views.md)除外。 您可以使用此維度和這兩個量度，檢視您的其餘報表中會排除哪些機器人資料。

由於機器人報表會與報表套裝的其他資料分開，因此此維度僅支援下列維度和量度：

* [頁面](page.md)
* 以時間為基礎的維度（例如，[Day](day.md)、[Week](week.md)或[Month](month.md)）
* [機器人發生次數](../metrics/bot-occurrences.md)
* [機器人頁面檢視次數](../metrics/bot-page-views.md)

搭配此維度使用任何其他維度或量度不會傳回資料。

## 將資料填入此維度中

如果您已啟用[機器人規則](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)，此維度會自動收集資料。 如果您尚未啟用[!UICONTROL 機器人規則]，則此維度不會出現在Analysis Workspace中。

## 維度項目

每個維度專案都會列出符合IAB或自訂機器人規則條件的機器人名稱。
