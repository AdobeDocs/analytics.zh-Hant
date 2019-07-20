---
description: 選取「通用 (交易 ID)」類別，可整合訪客 ID。
seo-description: 選取「通用 (交易ID)」類別，可整合訪客 ID。
seo-title: 訪客 ID
solution: Analytics
subtopic: 資料來源
title: 訪客 ID
topic: 開發人員和實施
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 訪客 ID

選取「通用 (交易 ID)」類別，可整合訪客 ID。

See [Integrate Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

<p class="head"> <b>訪客 ID 維度</b> </p>

| 欄名稱 | 說明 |
|--- |--- |
| 訪客 ID | (必要) 獨特值，代表離線和線上系列的客戶。 |
| 日期 | 使用以下日期格式: MM/DD/YYYY/hh/mm/ss (例如 07/14/2017/06/00/00) |
| 追蹤代碼 | 追蹤代碼名稱。 |
| 類別 | 類別名稱。若您指定類別，則必須選取產品。 |
| 管道 | 管道名稱。 |
| eVarN | eVarN名稱。n 的有效值是整數 1 - 75。 |
| 產品 | 產品名稱。 |
| 狀態 | 州/省名。 |
| 郵遞區號 | 郵遞區號名稱。 |

**訪客 ID 量度**

| 欄名稱 | 說明 |
|--- |--- |
| 點進 | 追蹤代碼檢視次數。 |
| 購物車新增次數 | 購物車新增次數。 |
| 購物車開啟次數 | 購物車開啟次數。 |
| 購物車刪除次數 | 購物車移除次數。 |
| 購物車檢視 | 購物車檢視次數。 |
| 結帳 | 結帳次數。 |
| 事件 n | 事件 n 的發生次數。n 的有效值是整數 1 - 100。若您指定「檢視」事件，則必須指定對應的資料維度 (eVar)。例如，若加入 eVar2 檢視，則必須列出 eVar2 的值。 |
| eVarN檢視 | 檢視 eVar n 的次數。n 的有效值是整數 1 - 75。 |
| 價格 | 產品價格。 |
| 訂購 | 訂購次數。 |
| 產品檢視 | 產品檢視次數。 |
| 數量 | 售出件數。 |