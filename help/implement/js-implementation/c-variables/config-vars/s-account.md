---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics Implementation
solution: null
title: 動態變數
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.useForcedLinkTracking


 變數會判斷資料儲存及報告所在的報表套裝。

若傳到多個報表套裝 (多套裝標籤)，`s.account` 則可能會是以逗號分隔的值清單。報表套裝 ID 由 Adobe 決定。

## 參數

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|--- |--- |--- |--- |
| 40 位元組 | 在 URL 路徑中 | 不適用 | 不適用 |

每個報表套裝 ID 都必須符合[!DNL Admin Console]中建立的值。每個報表套裝 ID 的位元組數不可超過 40，但所有報表套裝的彙總值 (整份逗號分隔清單) 則無限制。

報告套裝是報告中最基本的區段層級。您可以在合同允許的情況下設定任意數量的報告套裝。每個報告套裝代表一組已在 Adobe 收集伺服器中填入的專用表格。報告套裝可透過 JavaScript 程式碼中的`s_account` 變數來識別。

在 [!DNL Analytics] 中，位於報表左上方的網站下拉式方塊會顯示目前的報表套裝。每個報表套裝都有一個唯一識別碼，名為報表套裝 ID。此`s_account`變數包含資料所要傳送到的一或多個報表套裝 ID。報表套裝 ID 值不會對 [!DNL Analytics] 使用者顯示，且必須由 Adobe 提供或核准，您才可使用。每個報表套裝 ID 都有一個相關聯的「好記名稱」，此名稱可在[!DNL Admin Console]的報表套裝區段中變更。

`s_account` 變數通常會在 JavaScript 檔案 (s_code.js) 內進行宣告。您可以在 HTML 頁面上宣告 `s_account` 變數；當 `s_account` 的值可能隨不同頁面而有所變更時，這是很常見的做法。`s_account` 變數屬於全域變數，因此應在納入 Adobe 的 JavaScript 檔案前進行宣告。若 `s_account` 在 JavaScript 檔案載入時並沒有值，則不會將任何資料傳送至 [!DNL Analytics]。

Adobe [!DNL DigitalPulse Debugger] 會在位於「影像」一字正下方之 URL 的路徑中顯示 `s_account` 的值，緊接在 /b/ss/ 後面。在某些情況下，`s_account` 的值也會顯示在網域中 (在 112.2o7.net 的前面)。路徑中的值是決定目標報表套裝的唯一值。下方的粗體文字顯示資料所傳送到的報表套裝，如同除錯程式中所顯示。請參閱[DigitalPulse 除錯程式](https://docs.adobe.com/content/help/zh-Hant/analytics/implementation/testing-and-validation/debugger.html).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## 語法和可能的值

報表套裝 ID 是 ASCII 字元的英數字串，長度不得超過 40 位元組。唯一可用的非英數字元是連字號。空格、句號、逗號與其他標點符號皆不准使用。此`s_account`變數可包含多個報表套裝，所有報表套裝都會從頁面接收資料。

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

`s_account` 的所有值都必須由 Adobe 提供或核准。

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

* 若 `s_account` 為空白、未宣告或包含非預期的值，則不會收集任何資料。
* `s_account` 變數是逗號分隔清單 (多套裝標籤)，請勿在報表套裝 ID 間放入空格。
* 若 [!UICONTROL s.dynamicAccountSelection] 已設為 *True*，則會使用 URL 來決定目標報表套裝。請使用 [!DNL DigitalPulse Debugger] 來決定目標報表套裝。

* 某些情況下可使用 [!DNL VISTA] 來更改目標報表套裝。使用第一方 Cookie 時，或您的網站擁有超過 20 個作用中報表套裝時，建議使用 [!DNL VISTA] 將資料重新路由或複製到其他報表套裝。

* `s_account` 一律宣告於 JS 檔案內，或在納入前一刻宣告。
