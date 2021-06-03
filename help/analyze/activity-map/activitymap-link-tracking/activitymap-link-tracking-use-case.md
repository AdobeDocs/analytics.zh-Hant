---
description: 您可透過使用 s_objectID 變數自訂連結 ID、自訂地區，以及自訂 AppMeasurement ActivityMap 模組檔案，來區別連結。
title: 區別參照相同連結 ID 和地區的連結
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 43fe4eb9-08fe-4e20-bc02-3f712c3dec1d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 59%

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
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
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

透過為頁面上的連結或連結位置建立唯一的物件ID `s_objectID`，您可以改善Activity Map追蹤，或使用Activity Map來報告連結類型或位置，而非連結URL。 如需 變數的詳細資訊，請按[此處](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html)。`s_objectID`

>[!IMPORTANT]
>
>請注意，在Activity Map中使用`s_objectID`時，必須在結尾加上分號(`;`)。
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
    Product1<br/>
     <br/>
     <br/>
    Product2<br/>
     <br/>
     <br/>
    Product3<br/>
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

您可以自訂地區，確保每個「購買」連結都定義自己的地區。 若要這麼做，請將`"id"`參數新增至每個「Buy」錨點標籤的其中一個父項。

>[!NOTE]
>並未嚴格限制一定要使用`"id"`參數作為區域標識符。 您也可以使用JavaScript變數`"s.ActivityMap.regionIDAttribute"`來設定自己的識別碼。
>
>
><table id="table_250DB52A869C466B942517BABA1C287B">
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
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
     <br/>
     <br/>
    Buy<br/>
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
    區域c&lt;a8/
     <br/>
     <br/><br/>
   </td>
  </tr>
 </tbody>
</table>

## 自訂 AppMeasurement ActivityMap 模組檔案 {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
請務必測試修改後的代碼，確保代碼可以正常運作。Adobe 對修改後代碼的行為概不負責。

以下是一些您可加入 AppMeasurement.js 檔案中的&#x200B;**一般**&#x200B;連結/地區函數範例 (修改形式)。

```
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

在呼叫`s.tl()`期間會傳遞`linkName`。

```
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
