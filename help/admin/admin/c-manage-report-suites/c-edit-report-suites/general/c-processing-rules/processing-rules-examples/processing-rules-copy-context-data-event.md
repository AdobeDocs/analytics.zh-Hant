---
description: 處理規則可以根據上下文資料變數觸發事件。
subtopic: Processing rules
title: 使用上下文資料變數設定事件
feature: Admin Tools
role: Admin
exl-id: f0af0e23-c08a-4f82-85b4-25064eeaa3c6
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 100%

---

# 使用上下文資料變數設定事件

處理規則可以根據上下文資料變數觸發事件。

上下文資料變數需以下列格式，在 AppMeasurement 中指定：

```
 s.contextData['search_term']
```

[!UICONTROL 「上下文變數」]清單包含在最近 30 天內，傳送至報表套裝的所有變數。如果您知道上下文資料變數的名稱但尚未將它傳送至目前的報表套裝，則可輸入變數名稱並按一下&#x200B;**[!UICONTROL 「新增變數名稱上下文資料」]**：

![](assets/add-context-variable.png)

下列規則定義會針對[「複製上下文資料變數至 eVar」](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)規則展開，以便對每個包含特定上下文資料變數的點擊設定事件：

| 規則集 | 值 |
|---|---|
| 條件 | 如果設定 &#39;search_term&#39; 上下文資料 |
| 動作 | 設定 &#39;searches&#39; 事件 |

例如：

![](assets/processing_rule_set_event.png)

請參閱實作說明中的[上下文資料變數](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html?lang=zh-Hant)。
