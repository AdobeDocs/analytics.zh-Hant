---
title: ActivityMap.link
description: 自訂Activity Map收集連結點選的方式。
feature: Variables
role: Admin, Developer
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 8%

---

# ActivityMap.link

`ActivityMap.link`變數可讓您覆寫Activity Map用來設定連結值的邏輯。 此變數在您想要擁有比[`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md)提供的更多控制權的區域很有用。

>[!CAUTION]
>此變數會完全覆寫Activity Map邏輯。 在此設定覆寫函式並傳回不正確的值，可能會導致Activity Map維度和Activity Map覆蓋的資料收集問題。

## 使用Web SDK覆寫連結值

您可以使用[`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend)回呼來變更Web SDK裝載或中止傳送資料。

## 使用Adobe Analytics擴充功能覆寫連結

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的ActivityMap.link

將此變數指派給具有以下功能的函式：

* 接收被點按的HTML元素；及
* 傳回字串值。 此字串值是用於[Activity Map連結](/help/components/dimensions/activity-map-link.md)維度的最終值。

如果傳回值為[假](https://developer.mozilla.org/zh-TW/docs/Glossary/Falsy)，則會清除所有Activity Map內容資料變數，且不會追蹤任何連結資料。

## 範例

僅使用`<a>`標籤中的title屬性。 如果標題屬性不存在，則不會追蹤任何連結。

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

如果存在，則傳回`s.tl`中手動設定的連結名稱，否則傳回連結URL。

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele && ele.tagName == 'A' && ele.href) {
    return ele.href;
  }
}
```

您可以有條件地更改預設連結邏輯，而不是完全取代預設連結邏輯。

```html
<script>
  // Copy the original link function
  var originalLinkFunction = s.ActivityMap.link;
  // Return the link name from s.tl, a modified activity map value, or the original activity map value
  s.ActivityMap.link = function(element,linkName)
  {
    return linkName || customFunction(element) || originalLinkFunction(element,linkName);
  };
</script>

<button type="button" onclick="s.tl(this,'o',customFunction(this)">Add To Cart</button>
```

1. 如果傳遞了`linkName`，則方法已由`tl()`呼叫。 傳回以`linkName`傳入的`tl()`。
2. 當Activity Map呼叫時，永遠不會傳遞`linkName`，因此請使用連結元素呼叫`customFunction()`。 您可以使用任何想要傳回值的自訂函式。
3. 如果以上未傳回值，請使用一般收集作為遞補的連結名稱。
