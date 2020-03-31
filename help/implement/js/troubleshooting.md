---
title: 疑難排解 JavaScript 實施
description: 瞭解疑難排解 JavaScript 實施的常見問題和最佳實務。
translation-type: ht
source-git-commit: 8aa6932dcbb6dad88c27ba1cd4f5aad3bafcfc52

---


# 疑難排解 JavaScript 實施

以下是貴組織在將資料正確匯入 Adobe Analytics 時可能遇到問題的幾個原因。

## 使用引號

傳送至 Adobe 的變數大多為字串。在 JavaScript 中，您可以使用單引號或雙引號。

### 混合引號以定義變數

作為最佳實務，您使用的引號類型請務必保持一致。如果以單引號指定字串的開頭，就必須使用單引號來結束該字串。

例如 `s.eVar1 = 'Value'` 和 `s.eVar1 = "Value"` 都有效。`s.eVar1 = 'Value"` 無效.

### 在字串中包括單引號或雙引號

有時需要在字串中加入單引號或雙引號。例如需要在報表中加入 `Alex's sale` 或 `John the "Hunter"` 值時。有兩種方法可包含這些值：

* **使用其他引號類型**：例如 `s.eVar1 = "Alex's sale"` 和 `s.eVar1 = 'John the "Hunter"'` 都有效。
* **逸出引號**：使用反斜線來逸出引號。例如 `s.eVar1 = 'Alex\'s sale'` 和 `s.eVar1 = "John the \"Hunter\""` 都有效。

### 避免使用捲曲引號

有些程式會自動將中性引號 (`"..."` 和 `'...'`) 轉換為捲曲引號 (`“...”` 和 `‘...’`)。請避免使用文件編輯器 (例如 Microsoft Word)，或透過電子郵件傳送程式碼片段。JavaScript 中無法使用捲曲引號。

## 參考 Analytics 物件

所有傳送至 Adobe 的變數都會使用 Analytics 物件。大部分實施都使用 `s` 物件。請務必在參考您將 Analytics 物件納入參考的變數時加以確認。

例如 `s.eVar1 = 'Value'` 有效，而 `eVar1 = 'Value'` 非有效。

## 每個變數定義一次

追蹤函數 (`s.t()`) 執行時，AppMeasurement 會擷取所有已定義的變數，並將它們編譯為影像要求。如果您在實施中定義變數多次，則只會使用最新的值。請確定追蹤函數執行時，所有變數值都包含正確的值。

## 正確的變數大小寫

有些變數使用大寫字母。JavaScript 變數區分大小寫。請務必在定義變數時使用正確的大小寫。例如 `s.eVar1 = 'Value'` 有效，而 `s.evar1 = 'Value'` 非有效。

## 外掛程式

有些組織會使用外掛程式來改善 Adobe Analytics 的實施。升級 AppMeasurement 版本時，請勿忘記重新包含任何已安裝的外掛程式。在[!UICONTROL 代碼管理器]中建立的程式碼不含任何外掛程式的程式碼。製作現有程式碼的副本，以備您需要回復至舊版 AppMeasurement 時使用。

## 變數中的空白字元

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

在此情況下，`document.title` 會填入 `s.pageName`，而其會收到「Home Page」值。不過有些瀏覽器可能以不同方式解譯空格。結果可能是下列兩個範例之一：

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

在 Adobe Analytics 中，將這兩個變數值視為獨立個體，但是會自動移除空白字元以利顯示。結果報表會顯示兩個看似相同的「Home Page」行項目。請確定變數值中所需值的前後不含空白字元。
