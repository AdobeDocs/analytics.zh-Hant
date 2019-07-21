---
description: 說明如何啟用和實施銷售變數。
keywords: Analytics實作；銷售；變數；產品語法；轉換變數語法；s. products
seo-description: 說明如何啟用和實施銷售變數。
seo-title: 實作銷售變數
solution: Analytics
title: 實作銷售變數
topic: 開發人員和實施
uuid: 49e97dd0-e56 b-4d34-b274-8113b24 cb905
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 實作銷售變數

說明如何啟用和實施銷售變數。

## 啟用銷售變數 {#section_331B41FF5AED42F2AEFE043DD60238C7}

Merchandising can be enabled for any custom eVar on the **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Conversion Variables]** page (you no longer need to call Adobe):

![](assets/merch-enable.png)

| 設定 | 說明 |
|--- |--- |
| 過期時間 | 說明銷售值可持續多久。 |
| 銷售 | 產品語法: 值設定在 s.products 中。轉換變數語法: 值設定在指定的銷售 s.eVar 中。 |
| 銷售綁定事件 (僅限轉換變數語法) | 指出產品何時應繫結至目前銷售類別。按住 Ctrl 鍵並按一下清單中的多個項目，可以選取多個事件。注意: 選取「產品語法」時，不能選取事件 (事件將停用，但不會變成灰色)。選取「轉換變數語法」時，才能選取事件。 |

## 使用產品語法來實施 {#section_2774578D09CE40A093CB0D0A294DBF7C}

啟用「產品語法」時，銷售類別會直接填入產品變數，因此不需要選取和設定綁定事件。這是建議使用的方法，您也應使用此方法，除非在發生成功事件時無法將值用於設定 `s.products`。

* **語法**

```js
  s.products="category;product;quantity;price;event_incrementer; 
<codeph outputclass="syntax">
  eVarN=merch_category| 
 <codeph outputclass="syntax">
   eVarM=merch_category2" 
 </codeph outputclass="syntax"> 
</codeph outputclass="syntax">
```

* **範例**

```js
  s.events="prodView" 
  s.products=";Fernie Snow Goggles;;;; 
<codeph outputclass="syntax">
  eVar1=goggles" 
   In 
</codeph outputclass="syntax">
```

指派 eVar1 的值「護目鏡」給產品「Fernie 滑雪鏡」。與此產品相關的所有後續成功事件 (產品新增、結帳、購買等) 都評給「護目鏡」。

## 使用轉換變數語法來實施 {#section_6AE10F69F4A14636AB050BEA89A34E4E}

無法使用 eVar 值來設定 `s.products` 時，應使用轉換變數語法。這通常表示您的頁面沒有銷售管道或尋找方法的上下文。在這種情況下，您必須在到達產品頁面前先設定銷售變數，且值需持續到綁定事件發生為止。

當設定期間選取的綁定事件發生時，eVar 的持續值與產品相關。例如，如果指定 prodView 為綁定事件，銷售類別只有在發生事件時才繫結至目前產品清單。只有後續綁定事件才能更新已指派給產品的銷售 eVar。

* **語法** 在綁定事件的同一頁或上一頁:

   ```js
   s.eVar1="merchandising_category"
   ```

   在發生綁定事件的頁面上:

   ```js
   s.events="prodView" 
   s.products="category;product"
   ```

* **範例** 瀏覽的第 1 頁:

   ```js
   s.eVar1="Outdoors:Ski Goggles"
   ```

   瀏覽的第 2 頁:

   ```js
   s.events="prodView" 
   s.products=";Fernie Snow Goggles"
   ```

   指派 eVar1 的值「戶外:滑雪鏡」給產品「Fernie 滑雪鏡」。與此產品相關的所有後續成功事件 (產品新增、結帳、購買等) 都評給「護目鏡」。

此外，銷售變數的目前值繫結至所有後續產品，直到滿足下列條件之一:

* eVar 過期 (根據「過期時間」設定)
* 銷售 eVar 被新值覆寫。

如需詳細資訊，請參閱 [ 中的](https://analyticsdemystified.com/adobe-analytics/advanced-conversion-syntax-merchandising/)「進階轉換語法銷售」[!DNL analyticsdemystified.com]。
