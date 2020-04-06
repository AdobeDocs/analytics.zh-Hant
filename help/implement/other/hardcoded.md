---
title: 使用硬式編碼影像要求進行實施
description: 使用 HTML 影像標籤實施 Adobe Analytics (硬式編碼影像要求)
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 使用硬式編碼影像要求進行實施

Adobe 提供的 AppMeasurement 程式庫會編譯出現在頁面上的變數，然後以影像要求的形式傳送給 Adobe。您可以完全略過 AppMeasurement 程式庫，然後手動將影像要求傳送至 Adobe。此方法需要您手動制訂影像要求和查詢字串。

此實施方法可用於顯示外部來源影像的任何平台。它完全不依賴 JavaScript。

>[!NOTE] 雖然硬式編碼的影像要求易於設定，但在大型專案中卻難以除錯、維護和調整規模。繼續進行之前，請確定硬式編碼影像要求是您的最佳選項。

## 影像要求語法

以下是使用 HTML 的硬式編碼影像要求範例：

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` 指定通訊協定。比對影像要求中使用的通訊協定與您網站其他部分使用的通訊協定。
* `example.sc.omtrdc.net` 是 `trackingServer` 變數中包含的值。
* `/b/ss/` 包含在所有影像要求中。它屬於 Adobe 資料收集伺服器上所儲存影像的檔案結構的一部分。
* `examplersid` 是您傳送資料的目的地報表套裝 ID。
* `/1/` 是點擊來源。請參閱匯出使用手冊中[資料欄參考](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)底下的 `hit_source`。控制用來識別訪客的 Cookie 和其他方法之順序。
* 查詢字串分隔字元 (`?`) 後面的所有項目，都是您要納入報表的資料。如需影像要求中可包含參數的完整清單，請參閱[資料彙集查詢參數](../validate/query-parameters.md)。

## 常見問題集

瞭解使用硬式編碼影像要求的常見問題。

**查詢字串參數是否區分大小寫？**

是。請確定查詢字串參數完全一致，否則系統不會記錄。例如，`pagename` 不是有效的查詢字串參數，`pageName` 則有效。

**可以在查詢字串中加入空格嗎？**

每個查詢字串參數的值都會進行 URL 編碼。URL 編碼會將 URL 中通常不合規定的字元轉換為符合規定的字元。例如，空白字元可轉換為 `%20`。請確定所有非英數字元的都是以 URL 編碼。影像要求抵達資料收集伺服器時，Adobe 會自動對值進行 URL 解碼。

如需 URL 編碼運作方式的詳細資訊，請參閱 W3Schools 上的 [HTML URL 編碼參考](https://www.w3schools.com/tags/ref_urlencode.asp)。

**單一值最多可包含幾個字元？**

每個變數的長度上限均不同。大部分的流量變數可容納最多 100 個位元組，而轉換變數大多可容納最多 255 個位元組。影像要求抵達資料收集伺服器時，Adobe 會自動將這些值截斷至其長度上限。
