---
description: 處理規則可以根據上下文資料變數觸發事件。
seo-description: 處理規則可以根據上下文資料變數觸發事件。
seo-title: 使用上下文資料變數設定事件
solution: Analytics
subtopic: 處理規則
title: 使用上下文資料變數設定事件
topic: 管理工具
uuid: 4a6018eb-03e2-4ec-e48 bb-e48 bf716 e103
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 使用上下文資料變數設定事件

處理規則可以根據上下文資料變數觸發事件。

上下文資料變數需以下列格式，在 AppMeasurement 中指定:

```
 s.contextData['search_term']
```

[!UICONTROL 「上下文變數」]清單包含在最近 30 天內，傳送至報表套裝的所有變數。If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

The following rule definition expands on the [Copy a Context Data Variable to an eVar](../../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) rule to also set an event on every hit that contains a specific context data variable:

| 規則集 | 值 |
|---|---|
| 條件 | 如果設定 'search_term' 上下文資料 |
| 動作 | 設定 'searches' 事件 |

例如:

![](assets/processing_rule_set_event.png)

請參閱實施說明中的[上下文資料變數](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables)。
