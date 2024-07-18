---
description: 如果要使用通用變數 (例如 q) 填入搜尋詞，您可使用處理規則來以這些值填入內部搜尋詞 eVar。
subtopic: Processing rules
title: 使用查詢字串參數填入內部搜尋詞
feature: Admin Tools
role: Admin
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 100%

---

# 使用查詢字串參數填入內部搜尋詞

如果要使用通用變數 (例如 q) 填入搜尋詞，您可使用處理規則來以這些值填入內部搜尋詞 eVar。

查詢字串值必須編碼為 Unicode 或 UTF-8，處理規則才能讀取。

| 規則集 | 值 |
|---|---|
| 條件 | 如果查詢字串參數 q 已設定 |
| 動作 | 以查詢字串參數 q 覆寫內部搜尋詞的值 |

例如：

![](assets/populate-internal-search-terms.png)
