---
description: 您可使用處理規則讀取和寫入的可用維度和量度。
subtopic: Processing rules
title: 可用於處理規則的維度
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: 02fea12d1286fdf2b8cd075c8bcccca0d196cad2
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 13%

---

# 可用於處理規則的Dimension和量度

您可使用處理規則讀取和寫入的可用維度和量度。

## 自訂值和內容資料

| 值 | 讀取/寫入狀態 | 說明 |
| --- | --- | --- |
| 自訂值 | 唯讀 | 自訂文字或直接在處理規則的動作中輸入的值。 |
| 串連值 | 唯讀 | 結合兩個值所建立的值。 例如，管道和頁面名稱可以結合以建立子類別。 |

## 點選屬性

| 屬性 | 讀取/寫入狀態 | 說明 |
| --- | --- | --- |
| 頁面 URL | 讀取+寫入 | [頁面URL](/help/components/dimensions/page-url.md)維度。 連結追蹤點選在到達處理規則之前會移除此維度。 如果您使用處理規則重新插入頁面URL值，則點選會視為[頁面檢視](/help/components/metrics/page-views.md)，而非[頁面事件](/help/components/metrics/page-events.md)。 Adobe建議在修改頁面維度之前，先檢查頁面維度中的值。 |
| 頁面名稱 | 讀取+寫入 | [頁面](/help/components/dimensions/page.md)維度。 連結追蹤點選在到達處理規則之前會移除此維度。 如果您使用處理規則重新插入頁面值，則點選會視為[頁面檢視](/help/components/metrics/page-views.md)，而非[頁面事件](/help/components/metrics/page-events.md)。 Adobe建議在修改頁面維度之前，先檢查頁面維度中的值。 |
| 報表套裝 ID | 唯讀 | 處理規則執行所在的報表套裝。 此報告套裝可能與最初透過AppMeasurement傳送的報告套裝不同，例如使用VISTA規則時。 |
| AppMeasurement程式碼版本 | 唯讀 | 用來產生影像要求的AppMeasurement庫版本。 |
| IP 位址 | 唯讀 | 訪客的IP位址。 |
| 使用者代理 | 唯讀 | 訪客的使用者代理。 |
| 反向連結 | 唯讀 | [反向連結](/help/components/dimensions/referrer.md)維度。 |
| 查詢字串參數 | 唯讀 | 目前URL中指定查詢字串引數的值。 |
| 反向連結查詢字串引數 | 唯讀 | 反向連結URL中指定查詢字串引數的值，或空字串（如果不存在的話）。 |
| 反向連結網域 | 唯讀 | 反向連結URL的頁面網域，包括子網域。 |
| 反向連結根網域 | 唯讀 | 反向連結URL的頁面網域，不包括子網域。 |
| 頁面查詢字串 | 唯讀 | 目前URL中的所有查詢字串引數及其值。 |
| 反向連結查詢字串 | 唯讀 | 反向連結URL中的所有查詢字串引數及其值。 |
| 頁面路徑 | 唯讀 | 目前URL的頁面路徑。 頁面路徑不包含通訊協定、網域或查詢字串引數。 |
| 頁面網域 | 唯讀 | 目前URL的頁面網域，包括子網域。 頁面網域不包含頁面路徑或查詢字串引數。 |
| 頁面根網域 | 唯讀 | 目前URL的頁面網域，不包括子網域。 |
| 客戶角度 | 讀取+寫入 | 此旗標可確定點選是否為行動背景點選。 |

## 轉換變數

| 變數 | 讀取/寫入狀態 | 說明 |
| --- | --- | --- |
| eVar1-250 | 讀取+寫入 | [eVar](/help/components/dimensions/evar.md)維度。 |
| 促銷活動 | 讀取+寫入 | [追蹤代碼](/help/components/dimensions/tracking-code.md)維度。 |
| 購買 ID | 讀取+寫入 | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md)實作變數。 |
| 州別 | 讀取+寫入 | [`state`](/help/implement/vars/page-vars/state.md)實作變數已淘汰。 |
| Zip | 讀取+寫入 | [郵遞區號](/help/components/dimensions/zip-code.md)維度。 |
| 貨幣代碼 | 讀取+寫入 | [`currencyCode`](/help/implement/vars/config-vars/currencycode.md)實作變數。 重要：如果您將此變數設為無效值，點選會被捨棄。 |
| 交易 ID | 讀取+寫入 | [`transactionID`](/help/import/data-sources/transactionid.md)實作變數。 |

>[!NOTE]
>Adobe不支援使用處理規則設定[`products`](/help/implement/vars/page-vars/products.md)實作變數。

## 流量變數

| 變數 | 讀取/寫入狀態 | 說明 |
| --- | --- | --- |
| Prop 1-75 | 讀取+寫入 | [Prop](/help/components/dimensions/prop.md)維度。 |
| 階層 1-5 | 讀取+寫入 | [階層](/help/components/dimensions/hierarchy.md)維度。 |
| 伺服器 | 讀取+寫入 | [伺服器](/help/components/dimensions/server.md)維度。 |
| 管道 | 讀取+寫入 | [網站區段](/help/components/dimensions/site-section.md)維度。 |

## 內容變數

此報表套裝已在先前的影像要求中看到的所有[內容資料變數](/help/implement/vars/page-vars/contextdata.md)。 如果處理規則未將內容資料放入另一個變數，該資料會永久遺失。 如需使用範例，請參閱[將內容資料變數複製到eVar](processing-rules-examples/processing-rules-copy-context-data.md)和[使用內容資料變數設定事件](processing-rules-examples/processing-rules-copy-context-data-event.md)。

## 成功事件

處理規則可以設定事件，但無法將其讀取為條件。 將規則動作下拉式清單設定為&#x200B;**[!UICONTROL 設定事件]**&#x200B;以檢視可用的遞增量度。

| 變數 | 讀取/寫入狀態 | 說明 |
| --- | --- | --- |
| 訂購 | 僅寫入 | [訂單](/help/components/metrics/orders.md)量度。 |
| 購物車 | 僅寫入 | [購物車](/help/components/metrics/carts.md)量度。 |
| 購物車檢視 | 僅寫入 | [購物車檢視](/help/components/metrics/cart-views.md)量度。 |
| 結帳 | 僅寫入 | [結帳](/help/components/metrics/checkouts.md)量度。 |
| 購物車新增 | 僅寫入 | [購物車新增](/help/components/metrics/cart-additions.md)量度。 |
| 購物車移除 | 僅寫入 | [購物車移除](/help/components/metrics/cart-removals.md)量度。 |
| 事件 1-1000 | 僅寫入 | [自訂事件](/help/components/metrics/custom-events.md)。 |
| 產品瀏覽數 | 僅寫入 | [產品檢視](/help/components/metrics/product-views.md)量度。 |

