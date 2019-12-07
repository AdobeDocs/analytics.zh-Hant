---
description: 您可透過使用 s_objectID 變數自訂連結 ID、自訂地區，以及自訂 AppMeasurement ActivityMap 模組檔案，來區別連結。
title: 區別參照相同連結 ID 和地區的連結
topic: Activity map
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 區別參照相同連結 ID 和地區的連結

您可透過使用 s_objectID 變數自訂連結 ID、自訂地區，以及自訂 AppMeasurement ActivityMap 模組檔案，來區別連結。

舉例來說，假設您有多個「購買」連結，在 Activity Map 中以相同的連結 ID 和地區來識別:

<table id="table_3020E2C0175D455C84E794CF51BE5A93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 連結 ID </th> 
   <th colname="col3" class="entry"> 地區 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>Buy <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>recommendation Panel (建議面板) <p> </p> <p> </p> <p>recommendation Panel (建議面板) </p> <p> </p> <p> </p> <p>recommendation Panel (建議面板) </p> </td> 
  </tr> 
 </tbody> 
</table>

應如何自訂網頁和標記，以區別這些連結的值呢? 您有三個選擇: 自訂連結 ID、自訂地區，或是自訂 AppMeasurement ActivityMap 模組檔案。

## 使用 s_objectID 自訂連結 ID {#section_01B0D463397B4837B2D46F087A6E5937}

透過為頁面上的連結或連結位置建立唯一的物件 ID，可改善 Activity Map 追蹤，或使用 Activity Map 來報告連結類型或位置，而不是連結 URL。如需 s_objectID 變數的詳細資訊，請按[此處](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html)。

>[!IMPORTANT]
>
>請注意，在 Activity Map 中使用 s_objectID 時，必須在結尾加上分號 (;)。

<table id="table_9439A5F320304E439A19842CF3EBA456"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 連結 ID </th> 
   <th colname="col3" class="entry"> 地區 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt;&nbsp;&nbsp;&nbsp; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product1 <p> </p> <p> </p> <p>Product2 </p> <p> </p> <p> </p> <p>Product3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>recommendation Panel (建議面板) </p> <p> </p> <p> </p> <p>recommendation Panel (建議面板) </p> <p> </p> <p> </p> <p>recommendation Panel (建議面板) </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自訂地區 {#section_6B1EF302573B445DBAF44176D0A12DB9}

您可透過確定每個「購買」連結都定義自己的地區，來自訂地區。若要這麼做，請在每個 "Buy" 錨記的其中一個父項新增 "id" 參數。

> [!NOTE] 並未嚴格限制一定要使用 "id" 參數做為地區識別碼。您也可以使用 JavaScript 變數 "s.ActivityMap.regionIDAttribute" 設定自己的識別碼。

<table id="table_250DB52A869C466B942517BABA1C287B"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> 程式碼範例 </th> 
   <th colname="col2" class="entry"> 連結 ID </th> 
   <th colname="col3" class="entry"> 地區 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>region a <p> </p> <p> </p> <p>region b </p> <p> </p> <p> </p> <p>region c </p> </td> 
  </tr> 
 </tbody> 
</table>

## 自訂 AppMeasurement ActivityMap 模組檔案 {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>請務必測試修改後的代碼，確保代碼可以正常運作。Adobe 對修改後代碼的行為概不負責。

以下是一些您可加入 AppMeasurement.js 檔案的**一般**連結/地區函數範例 (修改形式)。

```
s.ActivityMap.link = function(ele,linkName){ 
if(linkName){ 
return linkName; 
} 
if(ele){ 
if(ele.tagName == 'A' && ele.href){ 
return ele.href; 
} 
} 
} 
```

linkName 是在呼叫 s.tl 時傳遞。

```
s.ActivityMap.region = function(ele){ 
var className, 
classNames = { 
'header': 1, 
'navbar': 1, 
'left-content': 1, 
'main-content': 1, 
'footer': 1, 
}; 
  while( (ele && (ele = ele.parentNode))){ 
if( (className=ele.className) && classNames[className]){ 
return className; 
} 
} 
return "BODY"; 
} 
```

