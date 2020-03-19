---
title: s_gi()
description: 建立及追蹤AppMeasurement的例項。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# s_gi

此函 `s_gi()` 數會依據報表套裝ID執行個體化或尋找AppMeasurement例項。 AppMeasurement keeps track of every instance created, and `s_gi()` returns the existing instance for a report suite if one exists. 如果實例不存在，則會建立新實例。

## s_gi()在Adobe Experience Platform Launch中

Analytics擴充功能會為您執行個體化及管理追蹤物件。 不過，您也可以在設定Adobe Analytics擴充功能時， [!UICONTROL Library Management] 在accordion中設定全域追蹤物件。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Extensions] ，然後按一下「Adobe Analytics [!UICONTROL Configure] 」下的按鈕。
4. 展開accordion [!UICONTROL Library Management] ，然後選擇除外的任何單選按鈕 [!UICONTROL Manage the library for me]。

全域變數文字欄位可讓您設定自訂追蹤物件。 Its default value is `s`.

## s_gi()在AppMeasurement和Launch自訂代碼編輯器中

呼叫函 `s_gi()` 數以實例化追蹤物件。 其唯一引數包含以逗號分隔的報表套裝ID字串。 報表套裝ID引數為必要參數。

> [!TIP] Adobe建議使用 `s` 變數作為追蹤物件。 Adobe在其 `s` 檔案、實作範例和外掛程式中使用。 但是，只要您在網站上保持一致，就可以使用任何變數。

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

> [!CAUTION] 以下章節和範例包含複雜的實施主題。 徹底測試您的實作並追蹤貴組織解決方案設計檔案中的重要 [自訂設定](../../prepare/solution-design.md)。

## 使用不同的追蹤物件來管理多個實施

如果您實例化多個追蹤物件，您可以傳送不同的資料至不同的報表套裝。 這兩個追蹤物件彼此獨立運作。

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

## 覆寫s物件後，還原AppMeasurement變數

某些協力廠商工具也可能會使用JavaScript物 `s` 件。 如果您不小心覆寫 `s` 網站上的物件，可以使用相同的RSID字串 `s_gi` 引數來呼叫，以還原所有已覆寫的變數和方法。

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

如果兩個變數參照相同 `s_gi()` 的函式與相同的報表套裝，則可以互換使用變數。

```js
// If the RSID is the same, any variables set in the 's' tracking object also get set in 'z' tracking object
var s = s_gi('examplersid');
var z = s_gi('examplersid');

s.eVar1 = "Shared tracking object value";

// This tracking call contains the above eVar1 value
z.t();
```
