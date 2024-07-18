---
title: 機器人名稱
description: 符合機器人規則的機器人名稱。
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
source-git-commit: 9f70dbeb9dfe54897915213480f05cbdfaf920ef
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 7%

---

# 機器人名稱

「機器人名稱」 [維度](overview.md)顯示使用[機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)偵測到的機器人名稱。 這些規則可以是預設IAB規則，或貴組織設定的自訂機器人規則。 若您想進一步瞭解哪些機器人正在造訪您的網站，或哪些機器人產生最多流量，則此功能會很有幫助。

系統會自動從所有的Analytics報表中篩選符合[!UICONTROL 機器人規則]的點選，但此維度、[機器人發生次數](../metrics/bot-occurrences.md)和[機器人頁面檢視次數](../metrics/bot-page-views.md)除外。 您可以使用此維度和這兩個量度，檢視您的其餘報表中會排除哪些機器人資料。

由於機器人報表會與報表套裝的其他資料分開，因此此維度僅支援下列維度和量度：

* [頁面](page.md)
* 以時間為基礎的維度（例如，[Day](day.md)、[Week](week.md)或[Month](month.md)）
* [機器人發生次數](../metrics/bot-occurrences.md)
* [機器人頁面檢視次數](../metrics/bot-page-views.md)

搭配此維度使用任何其他維度或量度不會傳回資料。

## 將資料填入此維度中

如果您已啟用[機器人規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)，此維度會自動收集資料。 如果您尚未啟用[!UICONTROL 機器人規則]，則此維度不會出現在Analysis Workspace中。

## 維度項目

每個維度專案都會列出符合IAB或自訂機器人規則條件的機器人名稱。
