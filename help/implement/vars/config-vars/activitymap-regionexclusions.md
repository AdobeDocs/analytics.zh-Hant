---
title: ActivityMap.regionExclusions
description: 依地區篩選Activity Map資料。
role: Admin, Developer
feature: Appmeasurement Implementation
exl-id: 353282aa-860c-45dc-a6b0-8d9f1fa09f13
TQID: https://experienceleague.adobe.com/zUbYze30ROCQXroX3h85fwC-YMzJDyTKpnMgealhAZA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 18%

---

# ActivityMap.regionExclusions

`ActivityMap.regionExclusions`變數可讓您根據在[Activity Map地區](/help/components/dimensions/activity-map-region.md)維度中收集的維度專案，選擇性地篩選或排除Activity Map資料。

## 網頁SDK擴充功能中的地區排除

當&#x200B;**[!UICONTROL 啟用點選資料集合]**&#x200B;啟用時，請使用&#x200B;**[!UICONTROL 篩選點選屬性]**&#x200B;回呼程式碼區塊。 在此程式碼區塊中，您可以檢查`content.linkRegion`的值，然後變更值或放棄連結追蹤資料的集合。

## 網頁SDK JavaScript資料庫中的地區排除

啟用[`clickCollectionEnabled`](https://experienceleague.adobe.com/tw/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)時，請在`clickCollection`物件中使用`filterClickDetails`回呼。 在此回撥中，您可以檢查`linkRegion`的值，然後變更值或放棄連結追蹤資料的集合。

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the clicked region has personal links in it, don't send click data
      if(content.linkRegion.includes("personal")) {
        return false;
      }
    }
  }
});
```

## 使用Adobe Analytics擴充功能的地區排除

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## 使用AppMeasurement的s.ActivityMap.regionExclusions

`s.ActivityMap.regionExclusions`變數是字串，其中包含要從Activity Map追蹤排除的逗號分隔片語。 如果任何片語符合在[Activity Map區域](/help/components/dimensions/activity-map-region.md)維度中收集的值，則所有Activity Map資料都會從點選中移除。

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.regionExclusions = "contact";
</script>

<!-- Clicking any of these links tracks normally. -->
<!-- While "contact" is present, it is not tracked in region. The region is "nav" -->
<nav>
  <a href="index.html">Home</a>
  <a href="products.html">View our products</a>
  <a href="contact.html">Contact us</a>
</nav>

<!-- Activity Map data is not tracked for any of these links. -->
<!-- All these links belong to the region "Personal contact information" -->
<div id="personal-contact-information">
 <a href="mailto:user@example.com">Example user</a>
 <a href="mailto:user2@example.com">Example user 2</a>
 <a href="mailto:user3@example.com">Example user 3</a>
</div>
```
