---
title: ActivityMap.region
description: 自訂Activity Map收集所點按地區的方式。
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 13%

---

# ActivityMap.region

`ActivityMap.region`變數可讓您覆寫Activity Map用來設定區域值的邏輯。 此變數在您想要擁有比[`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md)提供的更多控制權的區域很有用。

>[!CAUTION]
>此變數會完全覆寫Activity Map邏輯。 在此設定覆寫函式並傳回不正確的值，可能會導致Activity Map維度和Activity Map覆蓋出現資料收集問題。

## 使用網頁SDK覆寫區域值

您可以使用[`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend)回呼來更改網頁SDK承載或中止傳送資料。

## 使用Adobe Analytics擴充功能覆寫區域

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement中的ActivityMap.region和Analytics擴充功能自訂程式碼編輯器

將此變數指派給具有以下功能的函式：

* 接收被點按的HTML元素；及
* 傳回字串值。 此字串值是用於[Activity Map地區](/help/components/dimensions/activity-map-region.md)維度的最終值。

如果傳回值為[假](https://developer.mozilla.org/zh-TW/docs/Glossary/Falsy)，則會清除所有Activity Map內容資料變數，且不會追蹤任何連結資料。

## 範例

以小寫標籤名稱作為區域：

```js
s.ActivityMap.region = function(clickedElement) {
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    var regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

使用特定的所需類別名稱作為區域：

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
    if ((className = ele.className)) {
      let classes = className.split(' ');
      for (let i = 0; i < classes.length; i++) {
        if (classNames[classes[i]]) {
          return classes[i];
        }
      }
    }
  }
  return "BODY";
}
```
