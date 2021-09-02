---
title: Util.getQueryParam
description: 傳回查詢字串參數的值。
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '260'
ht-degree: 100%

---

# Util.getQueryParam

瀏覽器 URL 中的查詢字串參數常包含 Analytics 的重要資料。使用 `Util.getQueryParam()` 方法可擷取查詢字串中的資料。

## 使用 Adobe Experience Platform 中的標記取得查詢字串參數資料

您可以在資料元素中設定值，藉此取得查詢字串參數資料。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 資料元素]標記，然後按一下所需的資料元素 (或建立資料元素)。
4. 將 [!UICONTROL 「擴充功能」]下拉式清單設定為[!UICONTROL 「核心」]，並將[!UICONTROL 「資料元素類型」]設定為[!UICONTROL 「查詢字串參數」]。
5. 在文字欄位中輸入查詢字串參數。

查詢字串參數值會儲存在資料元素中。接著，您可以參考規則中的資料元素來指派 Analytics 變數。

## AppMeasurement 和自訂程式碼編輯器中的 s.Util.getQueryParam()

呼叫 `s.Util.getQueryParam()` 方法，從瀏覽器 URL 擷取查詢字串值。包含查詢字串參數的字串引數為必要項目。此方法會傳回字串，您可將其指派給 Analytics 變數：

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

第二個選用引數可讓您指定要檢查查詢字串參數的字串。依預設，公用程式會審視瀏覽器 URL。

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

第三個選用引數可讓您自訂查詢字串分隔字元。其預設值為 `&`。如果您的查詢字串使用不同的分隔字元，可以變更此值。

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
> 提供類似的外掛程式 [`s.getQueryParam`](../plugins/getqueryparam.md)。此外掛程式包含更進階的功能，但也更複雜，預設不在 AppMeasurement 中。
