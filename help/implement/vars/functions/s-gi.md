---
title: s_gi()
description: 建立及追蹤 AppMeasurement 的例項。
feature: Appmeasurement Implementation
exl-id: f87eff07-7e60-480b-8334-3db538c1030e
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 100%

---

# s_gi

`s_gi()` 函數會依據報表套裝 ID 將 AppMeasurement 的例項實例化或尋找例項。AppMeasurement 可追蹤已建立的所有例項，而 `s_gi()` 會傳回報表套裝的現有例項 (若存在)。如果例項不存在，則會建立新例項。

## 使用 Web SDK 擴充功能實例化追蹤物件

Web SDK 擴充功能會替您將追蹤物件實例化並進行管理。但是，您可以在擴充功能設定中自訂追蹤物件名稱：

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往「[!UICONTROL 擴充功能]」索引標籤，然後按一下 Adobe Experience Platform Web SDK 下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 將[!UICONTROL 名稱]欄位變更為所需的值。其預設值為 `alloy`。

## 實例化手動實作 Web SDK 的追蹤物件

以下程式碼會載入 Web SDK 並實例化追蹤物件。將內嵌指令碼尾端的字串 `"alloy"` 變更為所需的值，即可自訂追蹤物件名稱。

```js
<script>
  !function(n,o){o.forEach(function(o){n[o]||((n.__alloyNS=n.__alloyNS||
  []).push(o),n[o]=function(){var u=arguments;return new Promise(
  function(i,l){n[o].q.push([i,l,u])})},n[o].q=[])})}
  (window,["alloy"]);
</script>
<script src="https://cdn1.adoberesources.net/alloy/2.6.4/alloy.min.js" async></script>
```

如需詳細資訊，請參閱 Web SDK 文件中的[安裝 SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hant)。

## 使用 Adobe Analytics 擴充功能實例化追蹤物件

Analytics 擴充功能會替您將追蹤物件實例化或進行管理。不過，在設定 Adobe Analytics 擴充功能時，您也可以在[!UICONTROL 「資料庫管理」]摺疊式功能表中設定全域追蹤物件。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL 「資料庫管理」]摺疊式功能表，接著選取[!UICONTROL 「為我管理資料庫」]以外的任何選擇鈕。

全域變數文字欄位可讓您設定自訂追蹤物件。其預設值為 `s`。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s_gi()

呼叫 `s_gi()` 函數將追蹤物件實例化。其唯一引數包含以逗號分隔的報表套裝 ID 字串。報表套裝 ID 引數為必要項目。

>[!TIP]
>
>Adobe 建議使用 `s` 變數作為追蹤物件。Adobe 在自己的文件、實施範例和外掛程式中都使用 `s`。然而，只要在網站上保持一致，您可以使用任何變數。

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION]
>
> 以下章節和範例包含複雜的實施作業主題。請徹底測試您的實施，以及追蹤貴組織[解決方案設計文件](../../prepare/solution-design.md)中的重要自訂項目。

## 使用不同的追蹤物件來管理多個實施

如果您將多個追蹤物件實例化，可以傳送不同的資料至不同的報表套裝。這兩個追蹤物件彼此獨立運作。

```js
// Instantiate two separate tracking objects to two different report suites
var s = s_gi('examplersid1');
var z = s_gi('examplersid2');

// The s object and z object contain their own independent Analytics variables simultaneously
s.pageName = "Example page name 1";
z.pageName = "Example page name 2";

// Send data to the examplersid1 report suite
s.t();

// Send data to the examplersid2 report suite
z.t();
```

## 覆寫 s 物件後還原 AppMeasurement 變數

某些協力廠商工具可能也會使用 JavaScript `s` 物件。如果您不小心覆寫網站上的 `s` 物件，可以呼叫 `s_gi` 並搭配相同的 RSID 字串引數，還原所有遭到覆寫的變數和方法。

```js
// Step 1: Instantiate the tracking object
var s = s_gi("examplersid");

// Step 2: Set eVar1
s.eVar1 = "Example value";

// Step 3: Accidentally overwrite the tracking object
s = "3rd party tool";

// Step 4: If you attempt to send a tracking call, an error is returned. Instead, re-instantiate the tracking object
s = s_gi("examplersid");

// Step 5: The previous values of all variables are preserved. You can send a tracking call and eVar1 is correctly set
s.t();
```

## 使用多個變數參考相同的追蹤物件

如果兩變數透過相同的報表套裝參考相同的 `s_gi()` 函數，您可以交互使用變數。

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
