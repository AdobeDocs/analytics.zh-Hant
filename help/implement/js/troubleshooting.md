---
title: 疑難排解JavaScript實施
description: 瞭解疑難排解JavaScript實作的常見問題和最佳實務。
translation-type: tm+mt
source-git-commit: 8aa6932dcbb6dad88c27ba1cd4f5aad3bafcfc52

---


# 疑難排解JavaScript實施

以下是貴組織在將資料正確匯入Adobe Analytics時可能遇到問題的幾個原因。

## 使用引號

傳送至Adobe的變數大多為字串。 在JavaScript中，您可以使用單引號或雙引號。

### 混合引號以定義變數

作為最佳實務，請務必符合您使用的引號類型。 如果單引號指定了字串的開頭，則必須使用單引號來關閉該字串。

例如，兩者 `s.eVar1 = 'Value'` 都 `s.eVar1 = "Value"` 有效。 `s.eVar1 = 'Value"` 無效.

### 在字串中包括單引號或雙引號

有時需要在字串中加入單引號或雙引號。 例如，您想要在報表中加入 `Alex's sale` 值 `John the "Hunter"` 或值。 有兩種方法可包含這些值：

* **使用其他報價類型**:例如， `s.eVar1 = "Alex's sale"` 和 `s.eVar1 = 'John the "Hunter"'` 都有效。
* **轉義引號**:使用反斜線來逸出引號。 例如， `s.eVar1 = 'Alex\'s sale'` 和 `s.eVar1 = "John the \"Hunter\""` 都有效。

### 避免使用大引號

有些程式會自動將中性引號(`"..."` 和 `'...'`)轉換為彎引號(`“...”` 和 `‘...’`)。 避免使用檔案編輯器（例如Microsoft Word），或透過電子郵件傳送程式碼片段。 JavaScript中無法使用大引號。

## 參考Analytics物件

所有傳送至Adobe的變數都會使用Analytics物件。 大部分實作都使用 `s` 物件。 請務必在參考您將Analytics物件納入參考的變數時加以確認。

例如， `s.eVar1 = 'Value'` 為有效，而 `eVar1 = 'Value'` 非有效。

## 定義每個變數一次

當追蹤函式(`s.t()`)執行時，AppMeasurement會擷取所有已定義的變數，並將它們編譯為影像請求。 如果您在實施中定義變數多次，則只會使用最新值。 請確定追蹤函式執行時，所有變數值都包含正確的值。

## 正確的變數大寫

有些變數使用大寫字母。 JavaScript變數會區分大小寫。 請務必在定義變數時使用正確的大小寫。 例如， `s.eVar1 = 'Value'` 為有效，而 `s.evar1 = 'Value'` 非有效。

## 外掛程式

有些組織會使用外掛程式來改善Adobe Analytics的實作。 升級AppMeasurement版本時，請勿忘記重新包含任何已安裝的外掛程式。 在「程式碼管理 [!UICONTROL 器」中建立的程式碼] ，其中沒有外掛程式程式碼。 製作現有程式碼的復本，以備您需要回復至舊版AppMeasurement時使用。

## 變數值中的空格

HTML 中有數個字元會產生空白字元。這些字元包括空格、定位字元和歸位字元 (或換行字元)。考量下列範例:

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

In this case, `document.title` populates `s.pageName`, which receives a value of &quot;Home Page&quot;. 不過，有些瀏覽器可以以不同方式解譯空白。 結果可以是下列兩個範例之一：

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

在Adobe Analytics中，這兩個變數值會視為個別。 但是，會自動移除空白字元以用於顯示。 結果會顯示兩個看似相同的「首頁」行項目的報表。 請確定變數值在所需值之前或之後不包含空格。
