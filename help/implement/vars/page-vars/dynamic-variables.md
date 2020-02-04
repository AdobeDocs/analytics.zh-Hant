---
title: 動態變數
description: 複製變數而不會增加影像要求長度。
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# 動態變數

動態變數可讓您將值從一個變數複製到另一個變數，而不會增加影像要求長度。 在多個變數中擷取相同資料時，這些變數很有幫助。

在舊版Analytics中，影像要求長度對於防止截斷資料非常重要。 AppMeasurement的改良功能可讓影像要求查詢字串變長，因此通常不需要動態變數。

動態變數支援影像要求中的查詢字串參數或HTTP標題。 如需 [參考之可用參數的完整清單](../../validate/query-parameters.md) ，請參閱資料收集查詢參數。 請參 [閱Wikipedia上的標準請求欄位](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) ，以取得可參考之可用HTTP請求欄位的完整清單。

當Adobe識別動態變數首碼時，會自動複製您報表套裝中的查詢字串或HTTP標題值。 此動作會在任何其他處理（包括處理規則和VISTA規則）之前進行。

> [!TIP] 複製變數時請留意字元上限。 例如，如果複製 `eVar1` 至 `prop1`, `prop1` 可以有截斷值，因為它有100位元組限制(而 `eVar1` 有255位元組限制)。

## Adobe Experience Platform Launch中的動態變數

您可以在接受字串的任何維度欄位中使用動態變數。 維度值通常會在設定Analytics擴充功能（全域變數）或在規則下設定。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「規 [!UICONTROL 則] 」標籤，然後按一下所要的規則（或建立規則）。
4. 在「 [!UICONTROL 動作]」下方，按一下現有  的Adobe Analytics - 「設定變數」動作，或按一下「+」圖示。
5. 將「延伸 [!UICONTROL 功能] 」下拉式清單設定為Adobe Analytics，並將「動作類型 [!UICONTROL 」設] 定為變數 。
6. 找出所需的維度值。

在文字欄位中置入動態變數首碼，後面接著您要參考的查詢字串參數或HTTP標題。 依預設，動態變數首碼為 `D=`。

## AppMeasurement和Launch自訂程式碼編輯器中的動態變數

動態變數是指派給其他變數的文字字串。 預設的動態變數首碼為 `D=`。 動態變數會區分大小寫。

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

> [!NOTE] 在除錯實施時，動態變數會顯示為字串。 值由Adobe資料收集伺服器在伺服器端複製。
