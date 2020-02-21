---
description: 如果要使用通用變數 (例如 q) 填入搜尋詞，您可使用處理規則來以這些值填入內部搜尋詞 eVar。
subtopic: Processing rules
title: 使用查詢字串參數填入內部搜尋詞
topic: Admin tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

