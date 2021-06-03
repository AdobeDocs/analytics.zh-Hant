---
description: 處理規則可以根據上下文資料變數觸發事件。
subtopic: Processing rules
title: 使用上下文資料變數設定事件
feature: 管理工具
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
exl-id: f0af0e23-c08a-4f82-85b4-25064eeaa3c6
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 95%

---

# 使用上下文資料變數設定事件

處理規則可以根據上下文資料變數觸發事件。

上下文資料變數需以下列格式，在 AppMeasurement 中指定：

```
 s.contextData['search_term']
```

[!UICONTROL 「上下文變數」]清單包含在最近 30 天內，傳送至報表套裝的所有變數。如果您知道上下文資料變數的名稱但尚未將它傳送至目前的報表套裝，則可輸入變數名稱並按一下&#x200B;**[!UICONTROL 「新增變數名稱上下文資料」]**：

![](assets/add-context-variable.png)

下列規則定義會針對[「複製上下文資料變數至 eVar」](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)規則展開，以便對每個包含特定上下文資料變數的點擊設定事件：

| 規則集 | 值 |
|---|---|
| 條件 | 如果設定 &#39;search_term&#39; 上下文資料 |
| 動作 | 設定 &#39;searches&#39; 事件 |

例如：

![](assets/processing_rule_set_event.png)

請參閱實作說明中的[上下文資料變數](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html)。
