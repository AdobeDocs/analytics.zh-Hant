---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 清單變數

也稱為清單變數 (List Var)。清單變數的運作方式與清單 Prop 類似，也允許相同影像要求中可有多個值。其運作方式也類似於 eVar，可獨立存留於其定義所在之影像要求外。您可以使用這些變數來檢視單一頁面上多個元素的因果關係，例如產品清單、期望清單、進階搜尋清單或顯示廣告清單等。


<!-- 

listN.xml (bob edit)

 -->

**考量事項**

* 清單變數會參照訪客瀏覽器中的 VisitorID Cookie 以記憶其值。
* 每次每名訪客可儲存至多 250 個數值。如果超出每位訪客 250 個值，系統會使用最近的 250 個值。上述值的有效期會依據清單變數的有效期設定。
* 每個分隔值最多可包含 255 個字元 (若使用多位元組字元則更低)。此為單一元素的最大長度。
* 此變數中沒有字元數上限。此限制唯一的例外是在使用較舊的 Internet Explorer 瀏覽器時，此類瀏覽器會對所有的 URL 要求施加 2083 個字元的限制。
* 每個報表套裝皆可使用三個清單變數。
* 要使用清單變數，必須要使 H23 程式碼或更高版本。
* 清單變數可以分類。
* 若在相同的影像要求中定義重複值，清單變數會對這些值的所有例項進行重複資料刪除。
* 點擊 (或頁面檢視) 層級是清單變數劃分最精細的層級。若您有某個清單變數在相同的影像要求中有三個值，有任何區段規則符合其中一值時，即會將這三個值都提取到報表中。相反地，若定義的排除規則符合單一值，則會將這三個值都排除。

**設定** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

您可從管理控制台存取設定並進行更新，無需連絡 Adobe 客戶服務:

1. 前往 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理員]** &gt; **[!UICONTROL 報表套裝]**
1. 選取報表套裝。
1. 按一下&#x200B;**[!UICONTROL 編輯設定]** &gt; **[!UICONTROL 轉換]** &gt; **[!UICONTROL 清單變數]**。

* **名稱**: 每個分隔值最多可包含 255 個字元 (若使用多位元組字元則更低)。此為單一元素的最大長度。
* **值分隔字元**: 在清單變數中用來分隔值的字元。最常用的分隔字元包括逗號、冒號、垂直線或類似字元。

   >[!NOTE]
   >
   >清單變數不支援使用多位元組字元做為分隔字元。分隔字元必須是單一位元組。

* **有效期**: 此項目類似於 eVar 有效期，可決定清單變數與轉換事件之間可產生關聯的時間長度。

   * **在頁面檢視或瀏覽層級**: 頁面檢視或瀏覽以外的成功事件將不會連結回清單變數內的任何值。
   * **根據日、週、月等時段**: 指定時段以外的成功事件將不會連結回清單變數內的任何值。此外也可定義自訂天數。
   * **特定轉換事件**: 任何在指定的特定事件之後引發的其他成功事件，都不會連結回清單變數內的任何值。
   * **從不**: 清單變數與成功事件之間沒有時間上的限制。

* **配置**: 此設定會決定成功事件將評價分配給值的方式: 

   * **完整**: 所有在變數的有效期之前定義的變數值，都會獲得成功事件的完整評價。
   * **線性**: 所有在變數的有效期之前定義的變數值，都會獲得轉換事件的分配評價。
   * 一律不會覆寫變數值，而會新增至獲得成功事件之評價的值。

* **值數目上限**: 指定此清單變數允許的作用中值數目。例如，若設為 3，則只會儲存擷取到的最後 3 個值，並捨棄所有先前的值。請注意，如果同一個點擊針對相同清單變數傳送了多個值，且您使用值數目上限設定了限制，則每個值會有相同的時間戳記，且無法保證將儲存哪個值。

   每次每名訪客可儲存至多 250 個數值。如果超出每位訪客 250 個值，系統會使用最近的 250 個值。上述值的有效期會依據清單變數的有效期設定。

   「值數目上限」設定可用於限制對特定值數目的歸因。例如，如果在瀏覽的第一頁將清單變數設為 "A,B,C"，接著在第二頁設為 "X,Y,Z"，則會根據分配方法將歸因分配給這 6 個值。如果您想將歸因限制給 "X,Y,Z"，則可將值數目上限設定為 3。

若要設定或編輯清單變數，請前往 **[!UICONTROL Analytics]** &gt; **[!UICONTROL 管理員]** &gt; **[!UICONTROL 報表套裝]** &gt; **[!UICONTROL 編輯設定]** &gt; **[!UICONTROL 轉換]** &gt; **[!UICONTROL 清單變數]**。

**實施範例** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

下列每個範例都使用逗號做為值的分隔字元。

**在清單變數內定義單一值:**

```js
s.list1="Cat";
```

**傳入多個值:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**將收入計入清單變數中:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

此結果會顯示三個收入各為 50 美元的明細項目。(頂端橫幅廣告、側邊廣告與內部促銷活動 1。)請注意，此報表的總計會對收入進行去重複化，因此總計也將呈現為 50 美元。

**將收入計入在瀏覽期間設定多次的清單變數中:**

**配置**: 完整

**過期**: 瀏覽

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 頁面 </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 頁面 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (未設定) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**結果**: 所有在瀏覽期間的任何時間點設定於清單 var1 中的值 (value1,value2,value3,value4,value5,value6)，都會獲得購買的完整評價。

