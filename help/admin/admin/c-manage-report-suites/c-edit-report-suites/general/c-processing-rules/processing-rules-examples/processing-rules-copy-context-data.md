---
description: 處理規則用於將上下文資料變數的值移至 prop 和 eVar。
subtopic: Processing rules
title: 複製上下文資料變數至 eVar
feature: Admin Tools
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
exl-id: f52c2c6c-da3d-43d6-be13-92d0820c93b4
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 100%

---

# 複製上下文資料變數至 eVar

處理規則用於將上下文資料變數的值移至 prop 和 eVar。若沒有處理規則，上下文資料變數就毫無意義，且不會填入 Analytics 的任何報表。

[!UICONTROL 「上下文變數」]清單包含在最近 30 天內，傳送至報表套裝的所有變數。如果您知道上下文資料變數的名稱但尚未將它傳送至目前的報表套裝，則可輸入變數名稱並按一下&#x200B;**[!UICONTROL 「新增變數名稱上下文資料」]**：

![新增](assets/add-context-variable.png)

以下範例接受 `search_term` 這個上下文資料變數後，會將其值放入 `eVar3`：

![若您要在網站上追蹤可下載檔案的連結，請將 ](assets/set-context-data.png)

如果只有少數幾個 eVar 可填入，上述範例非常實用。如果您的組織有數百個上下文資料變數，每個變數都需要專屬 eVar，建議使用條件陳述式。符合單一處理規則的條件陳述式有數十個，方便您的組織填入報表套裝中的所有 eVar，不需受限於 150 個處理規則的上限。

下列範例會將上下文資料變數 `testhierarchy` 填入 `prop7`，前提是 `testhierarchy` 已設定：

![有條件](assets/add-conditional.png)

如需詳細瞭解如何實作上下文資料變數，請參閱實作使用手冊中的[上下文資料變數](/help/implement/vars/page-vars/contextdata.md)。