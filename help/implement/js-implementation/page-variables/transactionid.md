---
description: 頁面變數會直接填入一份報告，如 pageName、List Props、List Variables 等。
keywords: Analytics Implementation
subtopic: Variables
title: 頁面變數
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# transactionID

[!UICONTROL 「整合資料來源」使用交易 ID 將離線資料連接到線上交易 (像是在線上產生的潛在客戶或購買)。]


<!-- 

transactionID.xml

 -->

每個傳送至 Adobe 的唯一 *`transactionID`* 都會記錄下來，以便[!UICONTROL 資料來源]上傳有關該交易的離線資訊。請參閱 [Data Sources](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 100 位元組 | xact | 不適用 | "" |

**啟用交易 ID 儲存** {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

[!UICONTROL 交易 ID 儲存]必須於報表套裝管理員中選定的報表套裝啟用，才能記錄 *`transactionID`* 值。此設定位於

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

若要查看某個報表套裝是否已啟用 *`transactionID Storage`* 請前往

```
Analytics > Admin > Data Sources > Manage
```

**語法和可能的值** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

*`transactionID`* 只能包含英數字元。若有多個 [!UICONTROL transactionID] 變數應記錄在單一點擊中，您可以使用逗號來分隔多個值。

**範例** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**缺陷、問題和提示** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* 若未啟用 *`transactionID`* 記錄，則會捨棄 *`transactionID`* 值，且無法與[!UICONTROL 整合資料來源]搭配使用。請確保在設定 *`transactionID`* 的頁面上設定轉換變數或事件 (eVar 或 events 變數)。否則將不會為 *`transactionID`* 記錄任何資料。

* 如果您記錄多個系統的 [!UICONTROL transactionID] (例如購買和潛在客戶)，請確保 *`transactionID`* 中的值始終都是唯一的。要確保這一點，您可以為 ID 加上前置詞，如 lead_1234 與 purchase_1234。如果唯一的 *`transactionID`* 出現兩次，[!UICONTROL 整合資料來源]則無法如預期運作 ([!UICONTROL 資料來源]資料將連結至錯誤的資料)。

* 根據預設，建議將 *`transactionID`* 值設為 90 天。如果您的離線互動程序超過 90 天，請聯絡客戶服務以要求延長期限。

> [!NOTE]*`transactionID`* 變數可包含逗號以外的任何字元。其所在位置應與字元限制 (100 位元組) 的指定位置相同。若使用了多位元組字元，則必須啟用多位元組字元支援，以避免  *另存`transactionID`。*
