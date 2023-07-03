---
title: 資料來源檔案格式
description: 正確產生檔案以用於資料來源。
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 7%

---

# 資料來源檔案格式

資料來源檔案具有下列屬性：

* 檔案位於 `.txt` 格式。
* 註解的行開頭是&#39;`#`&#39;，和是選用專案。
* 第一個未註解的行包含檔案的標頭。
* 每一列的第一個值是日期，其格式為 `MM/DD/YYYY` 或 `MM/DD/YYYY/HH/mm/SS`.
* 每列的值（包括標題）均以定位字元分隔。
* 每一列必須至少有一個維度和一個量度。

## 註解

任何以「 」開頭的列`#`&#39;是註解。 下載資料來源範本檔案時，前兩行是註解。

* 第一個註解指出您為資料來源設定的範本型別、建立資料來源的後端使用者ID以及資料來源ID。
* 第二個註解為範本檔案中包含的每個標題提供易記名稱。

處理檔案時，所有註解列都會被Adobe忽略，因此您可以移除範本註解，或在整個檔案中新增您自己的註解列。 只能註解完整的列；您無法註解個別欄位或部分列。

## 標頭

上傳資料來源檔案時，需要欄標題。 這些欄標題不區分大小寫，但需要空格(例如， `eVar1` 是無效的標頭，而 `EVAR 1` 為有效)。 欄標題適用於所有報表套裝。 請使用下表確定資料來源檔案中的每個標題皆已正確設定。

>[!TIP]
>
>如果您在資料來源檔案中包含正確的標頭，您可以從頭開始建立資料來源檔案。 單一檔案中可包含的標頭數量沒有限制，但每列最多只能有4096個位元組。

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

Adobe不支援任何其他維度或量度的資料來源。 如果需要上述表格所列以外的變數，請考慮使用 [大量資料插入API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) 而非。

## 日期

每列中的第一個值 **必須** 為日期。 日期格式必須是下列格式之一：

* **`MM/DD/YY/HH/mm/SS`**
* **`MM/DD/YY`**

省略小時/分鐘/秒會自動將當天的時間戳記設定為中午12點。

單一資料來源檔案最多可支援90天不重複檔案。 如果您想在上傳中包含90天以上的不重複資料，請將資料分割為多個檔案。

## Dimension和量度資料

每列中日期之後的後續值都會包含您要上傳的資料。 每一列都會對應至該個別的時間戳記。 請確定每一列上的索引標籤數量相同。 欄可依任何順序排列；請確定每列中的資料都與頂端的標題對齊。 單列最多可包含4096個位元組。

Dimension資料不可包含分號(`;`)。 包含分號的列會被略過。

## 後續步驟

[檔案上傳](file-upload.md)：瞭解上傳資料來源檔案以供透過Adobe擷取的程式。
