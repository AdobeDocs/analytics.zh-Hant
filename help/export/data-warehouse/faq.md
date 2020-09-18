---
title: 資料倉庫常見問答集
description: 資料倉庫的常見問題。
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---


# 資料倉庫常見問答集

資料倉庫的常見問題。

## 當我在建立請求時使用詳細程度下拉式清單時，我可以預期日期會採用何種格式？

在「資料倉儲」請求中套用詳細程度時，「日期」欄會新增至報表。 日期格式會依所選取的詳細程度而變更。

| 粒度 | 格式 | 範例 |
| --- | --- | --- |
| 每小時 | `mmmm d, yyyy` 小時 `H` | 1月1日， 20XX,0小時 |
| 每日 | `mmmm d, yyyy` | 20XX年1月1日 |
| 每週 | 週 `w, yyyy` | 第1週， 20XX |
| 每月 | `mmmm yyyy` | 1月20日XX |
| 每季 | `q` 季度 `yyyy` | 第1季20XX |
| 每年 | `yyyy` | 20XX |

## 維度的區段如何在Data Warehouse中運作？

當您在Data Warehouse中將區段當做維度使用時，報表會傳回包含或 `"0"` 下列欄 `"1"`:

* **`"0"`**:維度項目不符合區段的條件。
* **`"1"`**:維度項目符合區段的標準。
