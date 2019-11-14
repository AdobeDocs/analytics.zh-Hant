---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---



# 事件

 變數可用來記錄一般購物車成功事件以及自訂成功事件。

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> 最大尺寸 </th> 
   <th class="entry"> 偵錯器參數 </th> 
   <th class="entry"> 填充報表 </th> 
   <th class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 不限 </td> 
   <td> 事件 </td> 
   <td> <p>購物車事件 </p> <p>自訂事件 </p> </td> 
   <td> 不適用 </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL 事件]應被視為網站上的里程碑。成功事件最常會填入至程序的最終確認頁面上，例如註冊程序或商務通訊註冊。自訂事件可藉由以下面「可能的值」一節中所定義的文字值填入事件變數來定義。

根據預設，成功事件會設定為&#x200B;*計數器*&#x200B;事件。計數器事件會計算成功事件的設定次數 (x+1)。事件也可設定為&#x200B;*數值*&#x200B;事件。數值事件可讓您指定所要增加的數值 (可能會在計算動態值或任意值時用到，例如內部搜尋所傳回的結果數)。

最後一個事件類型是&#x200B;*貨幣*，可讓您定義所要增加的金額 (類似於數值事件)，但在報表中會以貨幣的形式顯示，且必須遵循以 s.*`currencyCode`* 值和報表套裝預設貨幣設定為基礎的貨幣轉換方式。如需使用數值和貨幣事件的相關資訊，請參閱[產品](/help/implement/js-implementation/c-variables/page-variables.md)。

**設定變數** {#section_9195286C34C54B02B2598E2B856492C3}

依預設會為所有實施啟用 [!UICONTROL s.events] 變數。對於所有新的報表套裝，都會自動啟用七項預先設定的轉換事件。新的自訂事件 (event1- [event100 或 event1000](/help/implement/js-implementation/c-variables/page-variables.md)) 可由任何管理層級使用者透過管理控制台來啟用。

**可能的值** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

以下列出事件變數可使用的值: 

| 事件 | 說明 | 填充報表 |
|---|---|---|
| prodView | 產品檢視 | 產品 |
| scOpen | 開啟/初始化新的購物車 | 購物車 |
| scAdd | 將項目新增至購物車 | 購物車新增 |
| scRemove | 從購物車中移除項目 | 購物車移除 |
| scView | 檢視購物車 | 購物車檢視 |
| scCheckout | 結帳程序開始 | 結帳 |
| 購買 | 購買 (訂購) 完成 | 訂購 |
| event1 - event1000 (單點產品為 event100) | 自訂事件 | 自訂事件 |

**語法和範例** {#section_45A159DF00114066B8551DDEB15E084C}

計數器事件的設定方式，是將所需事件放入 [!UICONTROL s.events] 變數中 (若要傳送多個事件，則需使用逗號分隔清單)。

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

若是使用 H23 程式碼或更高版本，則可為計數器事件指派大於一的整數。

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

以指派的整數值實施計數器事件時，會將事件視為在影像要求內引發了多次。計數器事件不允許使用小數 - 如需使用此功能，建議您改用數值事件。數值和貨幣事件雖然通常會透過 [!UICONTROL s.products] 變數接收其數值 (例如 24.99)，但這些事件必須包含在 [!UICONTROL s.events] 變數中。如此可讓您將特定數值和貨幣值連結至個別的產品項目。

**事件序列化** {#section_A89488EF4471405AAFC4D6DD05E77621}

根據預設，每次在您的網站上設定事件時，都會對該事件計數。

請參閱[事件序列化](/help/implement/js-implementation/event-serialization.md)，以瞭解詳細資訊。

**語法** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**範例** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```
