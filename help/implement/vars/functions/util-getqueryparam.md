---
title: Util.getQueryParam
description: 傳回查詢字串參數的值。
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Util.getQueryParam

瀏覽器URL中的查詢字串參數常會包含Analytics的重要資料。 使用方 `Util.getQueryParam` 法從查詢字串擷取資料。

## 在Adobe Experience Platform Launch中取得查詢字串參數資料

您可以在資料元素中設定值，以取得查詢字串參數資料。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「資 [!UICONTROL 料元素] 」標籤，然後按一下所需的資料元素（或建立資料元素）。
4. 將「擴 [!UICONTROL 展] 」下拉式清單設 [!UICONTROL 為「核心]」，將「 [!UICONTROL 資料元素類型」設]為「查詢字串參數」。
5. 在文本欄位中輸入查詢字串參數。

查詢字串參數值儲存在資料元素中。 然後，您可以參考規則中的資料元素來指派Analytics變數。

## AppMeasurement和Launch自訂代碼編輯器中的s.Util.getQueryParam()

呼叫方 `s.Util.getQueryParam()` 法，從瀏覽器URL擷取查詢字串值。 包含查詢字串參數的字串引數為必填項。 此方法會傳回字串，您可將其指派給Analytics變數：

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

第二個可選引數可讓您指定要檢查查詢字串參數的字串。 依預設，公用程式會檢視瀏覽器URL。

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

第三個可選引數可讓您自訂查詢字串分隔字元。 Its default value is `&`. 如果您的查詢字串使用不同的分隔字元，則可以變更此值。

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

> [!NOTE] 舊版AppMeasurement有一個名為可用的外掛程 `s.getQueryParam` 式。 此外掛程式不再需要，因為現在預設會包含在AppMeasurement中。
