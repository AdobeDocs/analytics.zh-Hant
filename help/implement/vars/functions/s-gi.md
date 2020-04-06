---
title: s_gi()
description: 建立及追蹤 AppMeasurement 的例項。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# s_gi

`s_gi()` 函數會依據報表套裝 ID 將 AppMeasurement 的例項實例化或尋找例項。AppMeasurement 可追蹤已建立的所有例項，而 `s_gi()` 會傳回報表套裝的現有例項 (若存在)。如果例項不存在，則會建立新例項。

## Adobe Experience Platform Launch 中的 s_gi()

Analytics 擴充功能會替您將追蹤物件實例化或進行管理。However, you can also set a global tracking object in the [!UICONTROL Library Management] accordion when configuring the Adobe Analytics extension.

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展開accordion [!UICONTROL Library Management] ，然後選擇除外的任何單選按鈕 [!UICONTROL Manage the library for me]。

全域變數文字欄位可讓您設定自訂追蹤物件。其預設值為 `s`。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s_gi()

呼叫 `s_gi()` 函數將追蹤物件實例化。其唯一引數包含以逗號分隔的報表套裝 ID 字串。報表套裝 ID 引數為必要項目。

>[!TIP] Adobe 建議使用 `s` 變數作為追蹤物件。Adobe 在自己的文件、實施範例和外掛程式中都使用 `s`。然而，只要在網站上保持一致，您可以使用任何變數。

```js
// Instantiate the tracking object with a single report suite
var s = s_gi("examplersid");

// Instantiate the tracking object to send to multiple report suites
var s = s_gi("examplersid1,examplersid2");
```

>[!CAUTION] 以下章節和範例包含複雜的實施主題。請徹底測試您的實施，以及追蹤貴組織[解決方案設計文件](../../prepare/solution-design.md)中的重要自訂項目。

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

某些第三方工具可能也會使用 JavaScript `s` 物件。如果您不小心覆寫網站上的 `s` 物件，可以呼叫 `s_gi` 並搭配相同的 RSID 字串引數，還原所有遭到覆寫的變數和方法。

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
