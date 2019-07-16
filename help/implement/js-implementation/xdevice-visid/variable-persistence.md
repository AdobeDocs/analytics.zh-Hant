---
description: 若訪客資料在與相同的訪客 ID 變數產生關聯後合併，歷史資料集中的歸屬分配並不會變更。
keywords: Analytics 實施
seo-description: 若訪客資料在與相同的訪客 ID 變數產生關聯後合併，歷史資料集中的歸屬分配並不會變更。
seo-title: 歸因與持續性
solution: Analytics
title: 歸因與持續性
topic: 開發人員和實施
uuid: 5d706be-83f6-498a-a856-e3 c5 af995348
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 歸因與持續性

>[!IMPORTANT]
>
>不再建議這種識別跨裝置訪客的方法。Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

若訪客資料在與相同的訪客 ID 變數產生關聯後合併，歷史資料集中的歸屬分配並不會變更。

* 如果設定變數 `s.visitorID`，並在點擊時傳送，則系統會檢查是否有任何其他訪客資料具有相符的訪客 ID。
* 如果訪客資料存在，則自此之後都會使用系統中已存在的訪客資料，而不再使用先前的訪客資料。
* 如果找不到相符的訪客 ID，則會建立新的訪客資料。

當未驗證的客戶第一次造訪您的網站時，Adobe Analytics 會指派一個訪客資料給該客戶。如同[唯一訪客和瀏覽數](../../../implement/js-implementation/xdevice-visid/xdevice-connecting.md#section_70330AB6724C4E419A4BD0BDD54641AC)所示，驗證時會建立新的訪客資料。當建立新的訪客資料時，某個瀏覽會結束，而另一個瀏覽則會開始。

**在第一個資料連線上**

底下範例說明當使用者第一次在第一個裝置上進行驗證時，如何將資料傳送至 Adobe Analytics:

* `eVar16` 有效期為天，且瀏覽時 `evar17` 過期。

* `post_visitor_id` 欄代表由Adobe Analytics維護的描述檔。
* The `post_evar16` and `post_evar17` columns show shows the persistence of eVars.

* `cust_visid` 代表設定的值 `s.visitorID`。

* 每一列為一個「點擊」，此為傳送至 Adobe Analytics 資料收集伺服器的單一要求。

![](assets/xdevice_first.jpg)

在包含先前所無法識別之 `s.visitorID` 值 (`u999` 以上) 的第一個資料連線上，建立新的訪客資料。來自前一個訪客資料的持續性值會轉送至新的訪客資料。

* 設為瀏覽時即過期的 eVars 不會複製至已驗證的訪客資料。請注意，值 `car` 以上不會持續存在。
* 設為透過其他措施來過期的 eVars 將複製至已驗證的訪客資料。請注意，值 `apple` 持續存在。
* 對於持續存在的 eVars，不會記錄任何「例項」度量。這表示當使用交叉裝置訪客分身分識別時，可能看到 eVar 值的「唯一瀏覽」度量大於「例項」度量的報表。

**在後續的資料連線上**

底下範例說明先前在不同裝置上進行驗證之後，當客戶在新裝置上進行驗證時，如何將資料傳送至 Adobe Analytics。

![](assets/xdevice-subsequent.jpg)

當客戶驗證時，其 ID 符合先前「已驗證的」訪客資料 - `2947539300`。不再使用這個瀏覽開始時使用的訪客資料 (`5477766334477`)，而且來自檔案的資料不會持續存在。

* 地域劃分資料會根據第一次的瀏覽點擊進行記錄，不會因為單一瀏覽而變更，無論使用何種裝置皆然。這表示在新裝置的後續資料連線上，通常不會包括地域劃分資料。
* 在第一次瀏覽點擊時，會記錄如瀏覽器、作業系統及顏色深度這類的技術欄。如同地域劃分值一樣，它們將不會複製至裝訂的訪客資料。
* 通常設定為不要覆寫另一個通路的「行銷通路」(例如「直接」或「內部」)，將覆寫後續資料連線上的其他通路，其中包含該裝置的第一個驗證，例如[唯一訪客和瀏覽數](../../../implement/js-implementation/xdevice-visid/xdevice-connecting.md#section_70330AB6724C4E419A4BD0BDD54641AC)中顯示的第一個驗證。

**特殊情況**

在某些其他情況下，不會將資料從未驗證的訪客資料持續保存至已驗證的訪客資料。

* 如果使用者第一次瀏覽您的網站 (以前從未在此裝置上瀏覽過)，而且該使用者在到達後大約三分鐘內進行驗證，則沒有任何值將持續保存至已驗證的訪客資料。

