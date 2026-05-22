---
title: ActivityMap.regionIDAttribute
description: 變更Activity Map尋找的屬性以決定地區。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 4aec045e-1a86-412f-bd37-777ac49ccc7d
TQID: 'https://experienceleague.adobe.com/DJj1qmoYB0iMxDszdGKYTeczkjv0OvxXAYlg2irpKb0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 237
ht-degree: 15%

---

# ActivityMap.regionIDAttribute

`ActivityMap.regionIDAttribute`變數可讓您變更Activity Map在判斷[Activity Map地區](/help/components/dimensions/activity-map-region.md)維度時尋找的屬性。 如果網站的結構化方式讓`id`屬性對Activity Map區域不那麼有用，您可以設定此變數來檢視其他屬性。

## Web SDK擴充功能中的地區ID屬性

當&#x200B;**[!UICONTROL 啟用點選資料集合]**&#x200B;啟用時，請使用&#x200B;**[!UICONTROL 篩選點選屬性]**&#x200B;回呼程式碼區塊。 在此程式碼區塊中，您可以檢查`content.clickedElement`的值，然後變更值或放棄連結追蹤資料的集合。

## 網路SDK JavaScript資料庫中的地區ID屬性

啟用[`clickCollectionEnabled`](https://experienceleague.adobe.com/tw/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)時，請在`clickCollection`物件中使用`filterClickDetails`回呼。 在此回呼內，您可以檢查`clickedElement`的值，並自訂所收集區域的邏輯。

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

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

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
