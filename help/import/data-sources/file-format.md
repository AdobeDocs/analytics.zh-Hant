---
title: 資料來源檔案格式
description: 正確產生檔案以用於資料來源。
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 7%

---

# 資料來源檔案格式

資料源檔案具有以下屬性：

* 檔案位於 `.txt` 格式。
* 注釋行以「`#`&#39;和是可選的。
* 第一個非備注行包含檔案的標題。
* 每列的第一個值是日期，其格式為 `MM/DD/YYYY` 或 `MM/DD/YYYY/HH/mm/SS`.
* 每一列的值（包括標題）都以Tab分隔。
* 每列至少必須有一個維度和一個量度。

## 註解

任何以「開頭的行`#`&#39;是注釋。 下載資料來源範本檔案時，前兩行是註解。

* 第一個備注會指出您為資料來源設定的範本類型、建立資料來源的後端使用者ID，以及資料來源ID。
* 第二個註解會為範本檔案中包含的每個標題提供好記的名稱。

處理檔案時，Adobe會忽略所有注釋行，以便您可以刪除模板注釋或在整個檔案中添加自己的注釋。 只能對完整行進行注釋；您無法註解個別欄位或部分列。

## 標頭

上傳資料來源檔案時，需要欄標題。 這些欄標題不區分大小寫，但是需要空格(例如 `eVar1` 是無效的標題，而 `EVAR 1` 有效)。 欄標題會套用至所有報表套裝。 請使用下表來確認資料來源檔案中的每個標題皆已正確設定。

>[!TIP]
>
>如果您在資料來源檔案中加入正確的標題，可以從頭建立資料來源檔案。 單一檔案中可包含的標題數目沒有限制；不過，每列最多只能有4096個位元組。

| 維度 | 資料來源標題 |
| --- | --- |
| [類別](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [行銷管道](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [行銷管道詳細資料](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [產品](/help/components/dimensions/product.md) | `Product` |
| [追蹤代碼](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [交易 ID](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [郵遞區號](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Dimension和量度會進入相同的標題列。

| 量度 | 資料來源標題 |
| --- | --- |
| [購物車新增](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [購物車移除](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [購物車檢視](/help/components/metrics/cart-views.md) | `Cart Views` |
| [購物車](/help/components/metrics/carts.md) | `Cart Opens` |
| [結帳](/help/components/metrics/checkouts.md) | `Checkouts` |
| [自訂事件](/help/components/metrics/custom-events.md) | `Event 1` - `Event 1000` |
| [訂購](/help/components/metrics/orders.md) | `Orders` |
| [收入](/help/components/metrics/revenue.md) | `Price` |
| [件數](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

Adobe不支援任何其他維度或量度的資料來源。 如果需要上述表格中所列以外的變數，請考慮使用 [大量資料插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) 。

## 日期

每一列的第一個值 **必須** 是日期。 日期格式必須為下列其中一種格式：

* **`MM/DD/YY/HH/mm/SS`**
* **`MM/DD/YY`**

省略小時/分鐘/秒會自動將當天的時間戳記設為中午12點。

單一資料來源檔案最多可支援90個不重複日期。 如果您想在上傳中納入90天以上的不重複天數，請將資料分割為多個檔案。

## Dimension和量度資料

每一列中日期之後的後續值包含您要上傳的資料。 每一列都與各自的時間戳記對應。 請確定每一列都有相同數量的索引標籤。 欄可以按任意順序排列；請確定每列的資料都與頂端的標題對齊。 一列最大資料量為4096位元組。

Dimension資料不能包含分號(`;`)。 會略過包含分號的行。

## 後續步驟

[檔案上傳](file-upload.md):了解上傳資料來源檔案以依Adobe擷取的程式。