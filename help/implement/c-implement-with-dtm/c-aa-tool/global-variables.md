---
description: 使用動態標籤管理來部署 Adobe Analytics 時的欄位說明和變數相關資訊。
keywords: Dynamic Tag Management;全域變數;伺服器變數;eVar;Prop;動態變數首碼;動態變數
seo-description: 使用動態標籤管理來部署 Adobe Analytics 時的欄位說明和變數相關資訊。
seo-title: 全域變數
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: 全域變數
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 全域變數

使用動態標籤管理來部署 Adobe Analytics 時的欄位說明和變數相關資訊。

這些變數會在所有頁面載入規則信標上觸發。您可以透過設定為在所有頁面上觸發的[頁面載入規則](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706)來實現相同的效果。這些變數可能不會在[直接呼叫](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09)和[事件型](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC)規則中引發。

## 全域變數 - 欄位描述 {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]** &gt; ![](assets/settings_gear.png) **[!UICONTROL 編輯工具]** &gt; **[!UICONTROL 全域變數]**

| 元素 | 說明 |
|--- |--- |
| 伺服器 | 預先定義的變數會填入 Adobe Analytics 中的伺服器維度。請參閱[頁面變數](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVar | [eVar 變數](/help/implement/js-implementation/c-variables/page-variables.md)可用來建置自訂轉換報表。 |
| Prop | [Prop 變數](/help/implement/js-implementation/c-variables/page-variables.md)可用來建置自訂流量報表。 |
| 動態變數首碼 | 值開頭的特殊首碼。預設首碼為 "D="。請參閱[動態變數](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
