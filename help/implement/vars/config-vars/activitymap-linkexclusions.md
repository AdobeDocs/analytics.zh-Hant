---
title: ActivityMap.linkExclusions
description: 依連結名稱篩選Activity Map資料。
role: Admin, Developer
feature: Variables
exl-id: 9fc95016-362d-4c21-806e-e23adce9b6f7
source-git-commit: bcab98e453247c74b7d96497d34e6aea9ca32bc7
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 12%

---

# ActivityMap.linkExclusions

`ActivityMap.linkExclusions`變數可讓您根據[Activity Map連結](/help/components/dimensions/activity-map-link.md)維度中的文字，選擇性地篩選或排除Activity Map資料。

## Web SDK擴充功能中的連結排除

當&#x200B;**[!UICONTROL 啟用點選資料集合]**&#x200B;啟用時，請使用&#x200B;**[!UICONTROL 篩選點選屬性]**&#x200B;回呼程式碼區塊。 在此程式碼區塊中，您可以檢查`content.linkName`的值，然後變更值或放棄連結追蹤資料的集合。

## Web SDK JavaScript資料庫中的連結排除

啟用[`clickCollectionEnabled`](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)時，請在`clickCollection`物件中使用`filterClickDetails`回呼。 在此回撥中，您可以檢查`linkName`的值，然後變更值或放棄連結追蹤資料的集合。

```js
alloy("configure", {
  clickCollectionEnabled: true,
  clickCollection: {
    filterClickDetails: function(content) {
      // If the link is a clickable telephone number, anonymize it
      if(content.linkUrl.includes("tel:")) {
        content.linkName = content.linkUrl = "Phone number";
      }
      // If the link is an email address, anonymize it
      if(content.linkUrl.includes("mailto:")) {
        content.linkName = content.linkUrl = "Email address";
      }
    }
  }
});
```

## 使用Adobe Analytics擴充功能連結排除專案

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## 使用AppMeasurement的s.ActivityMap.linkExclusions

`s.ActivityMap.linkExclusions`變數是字串，其中包含要從Activity Map追蹤排除的短語逗號分隔值。 如果有任何短語符合在[Activity Map連結](/help/components/dimensions/activity-map-link.md)維度中收集的值，則所有Activity Map資料都會從點選中移除。 請注意，此變數會檢視`linkName`，而非`linkUrl`。

```html
<script>
  var s = s_gi("examplersid");
  s.ActivityMap.linkExclusions = "Contact";
</script>

<!-- Clicking this link tracks normally -->
<a href="products.html">View our products</a>

<!-- Activity Map data is not tracked for this link -->
<a href="mailto:user@example.com">Contact this user</a>
```
