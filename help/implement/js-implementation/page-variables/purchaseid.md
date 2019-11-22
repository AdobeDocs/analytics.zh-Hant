---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# purchaseID

 可用來防止報表中重複計算同一份訂單。


<!-- 

purchaseID.xml

 -->

只要您的網站上使用[!UICONTROL 購買]事件，則應使用 *`purchaseID`* 變數。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 20 位元組 | purchaseID | 轉換 &gt; 購買 &gt; 收入轉換 | "" |

當訪客在您的網站上購買商品時，*`purchaseID`* 即會在「感謝您」頁面中與引發[!UICONTROL 購買]事件相同的位置上填入。若已填入 *`purchaseID`*，每個 *`purchaseID`* 的「感謝您」頁面上的產品只會計算一次。這是很重要的，因為網站上會有許多訪客基於本身的用途而儲存「感謝您」或「確認」頁面。此&#x200B;*`purchaseID`* 可防止在每次檢視頁面時都計算一次購買數。

除了避免購買資料計算兩次，使用 *`purchaseID`* 時，會避免所有轉換資料在報表中重複計算。

**語法和可能的值** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

*`purchaseID`* 不可超過 20 個字元，且必須是標準 ASCII。

**範例** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**組態設定** {#section_1808631C96674380BF9C4A6D9A2C568E}

無

**缺陷、問題和提示** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

*`purchaseID`* 變數可讓頁面上所有的轉換變數在報表中僅計算一次。
