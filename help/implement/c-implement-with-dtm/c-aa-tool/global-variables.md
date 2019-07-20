---
description: 使用動態標籤管理來部署 Adobe Analytics 時的欄位說明和變數相關資訊。
keywords: 動態標籤管理；全域變數；伺服器變數；evar；prop；動態變數首碼；動態變數
seo-description: 使用動態標籤管理來部署 Adobe Analytics 時的欄位說明和變數相關資訊。
seo-title: 全域變數
solution: Marketing Cloud，Analytics，動態標籤管理
title: 全域變數
uuid: d759320a-96ee-4073-b5 fd-5257b7033003
translation-type: tm+mt
source-git-commit: 3489f00bd7dddefda0420fc361056416f6f10d3f

---


# 全域變數

使用動態標籤管理來部署 Adobe Analytics 時的欄位說明和變數相關資訊。

這些變數會在所有頁面載入規則信標上觸發。您可以透過設定為在所有頁面上觸發的[頁面載入規則](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706)來實現相同的效果。These variables might not fire in [Direct-Call](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) and [Event-Based](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC) rules.

## 全域變數 - 欄位描述 {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png)**[!UICONTROL 編輯工具]** &gt; **[!UICONTROL 全域變數]**

| 元素 | 說明 |
|--- |--- |
| 伺服器 | 預先定義的變數會填入Adobe Analytics中的伺服器維度。See [Page Variables](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVar | [eVar變數](/help/implement/js-implementation/c-variables/page-variables.md) 可用來建立自訂轉換報表。 |
| Prop | [Prop變數](/help/implement/js-implementation/c-variables/page-variables.md) 可用來建立自訂流量報表。 |
| 動態變數首碼 | 值開頭的特殊首碼。預設首碼為 "D="。See [Dynamic Variables](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
