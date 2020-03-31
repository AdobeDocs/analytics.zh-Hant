---
description: 使用 Dynamic Tag Management 來部署 Adobe Analytics 時的欄位說明和變數相關資訊。
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: 全域變數
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: ht
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# 全域變數

使用 Dynamic Tag Management 來部署 Adobe Analytics 時的欄位說明和變數相關資訊。

這些變數會在所有頁面載入規則信標上引發。您可以使用[頁面載入規則](/help/implement/other/dtm/c-rules/t-rules-page-conditions.md)集於所有頁面上引發，來達到相同的效果。這些變數可能不會在[直接呼叫](/help/implement/other/dtm/c-rules/t-rules-direct-conditions.md)和[事件型](/help/implement/other/dtm/c-rules/t-rules-event-conditions.md)規則中引發。

## 全域變數 - 欄位描述 {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]**>![](assets/settings_gear.png)**[!UICONTROL &#x200B;編輯工具&#x200B;]**>**[!UICONTROL &#x200B;全域變數&#x200B;]**

| 元素 | 說明 |
|--- |--- |
| 伺服器 | 預先定義的變數會填入 Adobe Analytics 中的伺服器維度。請參閱[伺服器](../../../vars/page-vars/server.md)。 |
| eVar | [eVar 變數](../../../vars/page-vars/evar.md)可用來建置自訂轉換報表。 |
| Prop | [Prop 變數](../../../vars/page-vars/prop.md)可用來建置自訂流量報表。 |
| 動態變數首碼 | 值開頭的特殊首碼。預設首碼為 &quot;D=&quot;。請參閱[動態變數](../../../vars/page-vars/dynamic-variables.md |
