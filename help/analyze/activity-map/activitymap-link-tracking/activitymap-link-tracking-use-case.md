---
description: 您可透過使用 s_objectID 變數自訂連結 ID、自訂地區，以及自訂 AppMeasurement ActivityMap 模組檔案，來區別連結。
title: 區別參照相同連結 ID 和區域的連結
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: User, Admin
exl-id: 43fe4eb9-08fe-4e20-bc02-3f712c3dec1d
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 57%

---

# 區別參照相同連結 ID 和地區的連結

您可透過使用 s_objectID 變數自訂連結 ID、自訂地區，以及自訂 AppMeasurement ActivityMap 模組檔案，來區別連結。

舉例來說，假設您有多個「購買」連結，在 Activity Map 中以相同的連結 ID 和地區來識別：

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
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td>
   <td colname="col2">
     <br/>
     <br/>
    購買<br/>
     <br/>
     <br/>
    購買<br/>
     <br/>
     <br/>
    購買<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    建議面板<br/>
     <br/>
     <br/>
    建議面板<br/>
     <br/>
     <br/>
    建議面板<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

應如何自訂網頁和標記，以區別這些連結的值呢？您有三個選擇：自訂連結 ID、自訂地區，或是自訂 AppMeasurement ActivityMap 模組檔案。

## 使用 s_objectID 自訂連結 ID {#section_01B0D463397B4837B2D46F087A6E5937}

建立唯一的物件ID後， `s_objectID`，若是頁面上的連結或連結位置，您可以改善Activity Map追蹤，或使用Activity Map來報告連結類型或位置，而非連結URL。 如需 變數的詳細資訊，請按[此處](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=zh-Hant)。`s_objectID`

>[!IMPORTANT]
>
>請注意，結尾是分號(`;`)時為必要項目 `s_objectID` Activity Map。

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
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt; </code><br/>
    <code>&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    產品1<br/>
     <br/>
     <br/>
    Product2<br/>
     <br/>
     <br/>
    產品3<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    建議面板<br/>
     <br/>
     <br/>
    建議面板<br/>
     <br/>
     <br/>
    建議面板<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## 自訂地區 {#section_6B1EF302573B445DBAF44176D0A12DB9}

您可以自訂地區，確保每個「購買」連結都定義自己的地區。 若要這麼做，請新增 `"id"` 參數至每個「購買」錨點標籤的其中一個父項。

>[!NOTE]
>
>您並未嚴格限制在 `"id"` 參數做為地區識別碼。 您也可以使用JavaScript變數來設定自己的識別碼 `"s.ActivityMap.regionIDAttribute"`.

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
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    購買<br/>
     <br/>
     <br/>
    購買<br/>
     <br/>
     <br/>
    購買<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    區域a<br/>
     <br/>
     <br/>
    區域b<br/>
     <br/>
     <br/>
    region c<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## 自訂 AppMeasurement ActivityMap 模組檔案 {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>請務必測試修改後的程式碼，以確保程式碼正常運作。 Adobe 對修改後代碼的行為概不負責。

以下是一些您可加入 AppMeasurement.js 檔案中的&#x200B;**一般**&#x200B;連結/地區函數範例 (修改形式)。

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

此 `linkName` 在呼叫時傳遞 `s.tl()`.

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  }; 
  while ((ele && (ele = ele.parentNode))) {
    if ((className=ele.className) && classNames[className]) {
      return className;
    }
  }
  return "BODY";
}
```
