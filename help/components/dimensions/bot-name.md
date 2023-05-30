---
title: 機器人名稱
description: 符合機器人規則的機器人名稱。
exl-id: 668c1dce-c603-477a-9df7-dacb649bbf63
source-git-commit: 5ba12c243a8013c52b487d048c54461ebdf7bd85
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# 機器人名稱

「機器人名稱」維度會顯示使用偵測到的機器人名稱 [機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). 這些規則可以是預設的IAB規則，或是您的組織所設定的自訂機器人規則。 若您想進一步瞭解哪些機器人正在造訪您的網站，或哪些機器人產生的流量最多，則此功能會很有幫助。

符合的點選 [!UICONTROL 機器人規則] 會自動從所有Analytics報表中篩選（此維度除外）， [機器人發生次數](../metrics/bot-occurrences.md)、和 [機器人頁面檢視](../metrics/bot-page-views.md). 您可以使用此維度和這兩個量度，檢視您的其餘報表中會排除哪些機器人資料。

由於機器人報表獨立於報表套裝的其餘資料，因此此維度僅支援下列維度和量度：

* [頁面](page.md)
* 以時間為基礎的維度(例如 [日](day.md)， [周](week.md)，或 [月](month.md))
* [機器人發生次數](../metrics/bot-occurrences.md)
* [機器人頁面檢視](../metrics/bot-page-views.md)

搭配此維度使用任何其他維度或量度不會傳回資料。

## 將資料填入此維度中

如果您已啟用 [機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)，此維度會自動收集資料。 如果您尚未啟用 [!UICONTROL 機器人規則]，此維度不會出現在Analysis Workspace中。

## 維度項目

每個維度專案都會列出符合IAB或自訂機器人規則條件的機器人名稱。
