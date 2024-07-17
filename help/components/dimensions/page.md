---
title: 頁面
description: 頁面名稱。
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 80%

---

# 頁面

「頁面」[維度](overview.md)會列出您網站上的頁面名稱。 這是 Adobe Analytics 中最常使用的維度之一，因為它可讓您深入分析網站上的哪些頁面表現最佳。

此維度與[網站區段](site-section.md)和[伺服器](server.md)維度有關。「頁面」最精細，「伺服器」最不精細，「網站區段」介於兩者之間。

## 將資料填入此維度中

此維度會擷取 [`pageName` 查詢字串](/help/implement/validate/query-parameters.md)中的資料，該字串位在[頁面檢視呼叫 (`t()`)](/help/implement/vars/functions/t-method.md) 中。 [連結追蹤呼叫 (`tl()`)](/help/implement/vars/functions/tl-method.md) 一律會移除此維度，即使 `pageName` 查詢字串存在也一樣。

AppMeasurement 會使用 [`pageName`](/help/implement/vars/page-vars/pagename.md) 變數收集這項資料。 如果未設定`pageName`變數，此維度會退回使用[`pageURL`](/help/implement/vars/page-vars/pageurl.md)變數。

## 維度項目

維度項目包含網站上頁面的名稱。您的組織會決定您要使用的特定維度專案。 有些組織會直接使用 `document.title`，有些則會制定自訂的階層連結。無論您使用何種方法，請確保其一致性，並確實將其記錄在[解決方案設計文件](/help/implement/prepare/solution-design.md)中。

>[!NOTE]
>
>Analysis Workspace 依預設會使用「最後」歸因，並提供使用任何歸因模型的選項。
