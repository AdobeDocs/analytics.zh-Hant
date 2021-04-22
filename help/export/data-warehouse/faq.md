---
title: Data Warehouse 常見問答
description: Data Warehouse 常見問答。
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '131'
ht-degree: 100%

---

# Data Warehouse 常見問答

Data Warehouse 常見問答。

## 當我建立請求並使用詳細程度下拉選單時，日期會採用哪一種格式？

在 Data Warehouse 請求中套用詳細程度時，「日期欄」會加至報告中。依所選的詳細程度，日期格式會有不同。

| 詳細程度 | 格式 | 範例 |
| --- | --- | --- |
| 每小時 | `mmmm d, yyyy` 小時 `H` | 20XX 年 1 月 1 日，小時 0 |
| 每日 | `mmmm d, yyyy` | 20XX 年 1 月 1 日 |
| 每週 | 週 `w, yyyy` | 20XX 年第 1 週 |
| 每月 | `mmmm yyyy` | 20XX 年 1 月 |
| 每季 | `q` 季度 `yyyy` | 20XX 年第一季 |
| 每年 | `yyyy` | 20XX |

## Data Warehouse 中如何將區段作為維度使用？

當您在 Data Warehouse 中使用區段作為維度時，報告會傳回一欄含有 `"0"` 或 `"1"`：

* **`"0"`**：該維度項目不符合區段標準。
* **`"1"`**：該維度項目符合區段標準。
