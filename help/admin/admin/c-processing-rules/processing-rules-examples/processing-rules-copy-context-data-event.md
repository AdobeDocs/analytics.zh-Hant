---
description: 處理規則可以根據上下文資料變數觸發事件。
subtopic: Processing rules
title: 使用上下文資料變數設定事件
topic: Admin tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# 使用上下文資料變數設定事件

處理規則可以根據上下文資料變數觸發事件。

上下文資料變數需以下列格式，在 AppMeasurement 中指定：

```
 s.contextData['search_term']
```

The [!UICONTROL Context Variables] list contains all variables that were sent to the report suite in the previous 30 days. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

下列規則定義會針對[「複製上下文資料變數至 eVar」](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)規則展開，以便對每個包含特定上下文資料變數的點擊設定事件：

| 規則集 | 值 |
|---|---|
| 條件 | 如果設定 &#39;search_term&#39; 上下文資料 |
| 動作 | 設定 &#39;searches&#39; 事件 |

例如：

![](assets/processing_rule_set_event.png)

請參閱實作說明中的[上下文資料變數](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html)。
