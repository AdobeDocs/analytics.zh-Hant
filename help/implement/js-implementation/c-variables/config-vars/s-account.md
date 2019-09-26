---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.account

 變數會判斷資料儲存及報告所在的報表套裝。

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. 報表套裝 ID 由 Adobe 決定。

## 參數

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 40 位元組 | 在 URL 路徑中 | 不適用 | 不適用 |

Each report suite ID must match the value created in the [!DNL Admin Console]. 每個報表套裝 ID 的位元組數不可超過 40，但所有報表套裝的彙總值 (整份逗號分隔清單) 則無限制。

報告套裝是報告中最基本的區段層級。您可以在合同允許的情況下設定任意數量的報告套裝。每個報告套裝代表一組已在 Adobe 收集伺服器中填入的專用表格。報告套裝可透過 JavaScript 程式碼中的`s_account` 變數來識別。

在 [!DNL Analytics] 中，位於報表左上方的網站下拉式方塊會顯示目前的報表套裝。每個報表套裝都有一個唯一識別碼，名為報表套裝 ID。此`s_account`變數包含資料所要傳送到的一或多個報表套裝 ID。報表套裝 ID 值不會對 [!DNL Analytics] 使用者顯示，且必須由 Adobe 提供或核准，您才可使用。Every report suite ID has an associated "friendly name" that can be changed in the report suites section of the [!DNL Admin Console].

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). 您可以在HTML `s_account` 頁面上宣告變數，這是當變數的值可能在頁面之間 `s_account` 變更時的常見做法。 Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. 在某些情況下， `s_account` of的值也會出現在網域中112.2o7.net之前。 路徑中的值是決定目標報表套裝的唯一值。下方的粗體文字顯示資料所傳送到的報表套裝，如同除錯程式中所顯示。請參閱 [DigitalPulse 除錯程式](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## 語法和可能的值

報表套裝 ID 是 ASCII 字元的英數字串，長度不得超過 40 位元組。唯一可用的非英數字元是連字號。空格、句號、逗號與其他標點符號皆不准使用。此`s_account`變數可包含多個報表套裝，所有報表套裝都會從頁面接收資料。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

Adobe必須提 `s_account` 供或核准所有值。

## 範例

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

## 在 Analytics 中設定變數

與各報表套裝 ID 相關聯的好記名稱，可由 Adobe [!DNL Customer Care] 進行變更。好記名稱可在 [!DNL Analytics] 中位於畫面左上方的網站下拉式方塊中檢視。

## 缺陷、問題和提示

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Use the [!DNL DigitalPulse Debugger] to determine the destination report suite(s).

* 某些情況下可使用 [!DNL VISTA] 來更改目標報表套裝。使用第一方 Cookie 時，或您的網站擁有超過 20 個作用中報表套裝時，建議使用 [!DNL VISTA] 將資料重新路由或複製到其他報表套裝。

* Always declare `s_account` inside the JS file or just before it is included.
