---
description: 選取「通用 (交易 ID)」類別，可整合交易 ID。
seo-description: 選取「通用 (交易 ID)」類別，可整合交易 ID。
seo-title: 交易 ID
solution: Analytics
subtopic: 資料來源
title: 交易 ID
topic: 開發人員和實作
uuid: f3370bb7-3f28-460b-a20 d-c9 e58 d7301 d
translation-type: tm+mt
source-git-commit: e9cb3575780db9eb5c9a766ef20d596e504a20d0

---


# 交易 ID

選取「通用 (交易 ID)」類別，可整合交易 ID。

請參閱 [整合離線資料](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6)。

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**交易 ID 維度**

| 欄名稱 | 說明 |
|--- |--- |
| 交易 ID | (必要) 獨特值，代表導致離線活動的線上交易。 |
| 日期 | 使用以下日期格式: MM/DD/YYYY/HH/mm/SS (例如 01/01/2015/06/00/00) |
| 追蹤代碼 | 追蹤代碼名稱。 |
| 類別 | 類別名稱。若您指定類別，則必須選取產品。 |
| 管道 | 管道名稱。 |
| eVarN | eVarN名稱。N的有效值為整數-250。 |
| 產品 | 產品名稱。 |
| 狀態 | 州/省名。 |
| Zip | 郵遞區號名稱。 |

<p class="head"> <b>交易 ID 維度</b> </p>



| 欄名稱 | 說明 |
|--- |--- |
| 點進 | 追蹤代碼檢視次數。 |
| 購物車新增次數 | 購物車新增次數。 |
| 購物車開啟次數 | 購物車開啟次數。 |
| 購物車刪除次數 | 購物車移除次數。 |
| 購物車檢視 | 購物車檢視次數。 |
| 結帳 | 結帳次數。 |
| eventN | eventN發生的次數。N的有效值為整數-1000。若您指定「檢視」事件，則必須指定對應的資料維度 (eVar)。例如，若加入 eVar2 檢視，則必須列出 eVar2 的值。 |
| eVarN檢視 | 檢視eVarN的次數。N的有效值為整數-250。 |
| 價格 | 產品價格。 |
| 訂購 | 訂購次數。 |
| 產品檢視 | 產品檢視次數。 |
| 數量 | 售出件數。 |
