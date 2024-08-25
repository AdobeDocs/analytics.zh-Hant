---
title: ActivityMap.regionIDAttribute
description: 變更Activity Map尋找的屬性以決定區域。
feature: Variables
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 11%

---

# ActivityMap.regionIDAttribute

`ActivityMap.regionIDAttribute`變數可讓您變更Activity Map在判斷[Activity Map地區](/help/components/dimensions/activity-map-region.md)維度時尋找的屬性。 如果網站的結構化方式讓`id`屬性對Activity Map區域不那麼有用，您可以設定此變數來檢視其他屬性。

## Web SDK擴充功能中的地區ID屬性

當&#x200B;**[!UICONTROL 啟用點選資料集合]**&#x200B;啟用時，請使用&#x200B;**[!UICONTROL 篩選點選屬性]**&#x200B;回呼程式碼區塊。 在此程式碼區塊中，您可以檢查`content.clickedElement`的值，然後變更值或放棄連結追蹤資料的集合。

## Web SDK JavaScript資料庫中的地區ID屬性

啟用[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)時，請在`clickCollection`物件中使用`filterClickDetails`回呼。 在此回呼內，您可以檢查`clickedElement`的值，並自訂所收集區域的邏輯。

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked element was in a table, set the region to the contents of the data-custom attribute
      // If the clicked element was not in a table, or if the data-custom attribute doesn't exist, leave region as-is
      content.region = content.clickedElement.closest('table')?.getAttribute('data-custom') || content.region;
    }
  }
});
```

## 使用Adobe Analytics擴充功能的地區ID屬性

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## 使用AppMeasurement的s.ActivityMap.regionIDAttribute

`s.ActivityMap.regionIDAttribute`變數是字串，代表決定[Activity Map地區](/help/components/dimensions/activity-map-region.md)維度的屬性。 此變數預設為`id`。 如果您變更此變數，Activity Map將不再尋找`id`屬性，但仍會尋找其他條件來判斷區域（例如語意元素）。

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionIDAttribute = "data-custom";
</script>

<!-- Clicking any of these links populates the region dimension with 'left-nav' -->
<div id="676967617A656C6C65" data-custom="left-nav">
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</div>
```
