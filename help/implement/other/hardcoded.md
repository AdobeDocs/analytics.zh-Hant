---
title: 使用硬式編碼影像要求實作
description: 使用HTML影像標籤（硬式編碼影像要求）實作Adobe Analytics
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 使用硬式編碼影像要求實作

Adobe提供的AppMeasurement程式庫會編譯出現在頁面上的變數，然後以影像要求的形式傳送給Adobe。 您可以完全略過AppMeasurement程式庫，然後手動傳送影像要求至Adobe。 此方法需要您手動制定影像請求和查詢字串。

此實作方法可用於任何顯示外部來源影像的平台。 它完全不依賴JavaScript。

> [!NOTE] 雖然硬式編碼影像要求易於設定，但在大型專案中卻難以除錯、維護和縮放。 繼續之前，請確定硬式編碼影像要求是您的最佳選項。

## 影像要求語法

以下是使用HTML的硬式編碼影像要求範例：

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` 指定協定。 將影像要求中使用的通訊協定與您網站其他使用者使用的通訊協定相符。
* `example.sc.omtrdc.net` 是變數中包含的 `trackingServer` 值。
* `/b/ss/` 包含在所有影像要求中。 它是儲存在Adobe資料收集伺服器上之影像的檔案結構的一部分。
* `examplersid` 是您要傳送資料至的報表套裝ID。
* `/1/` 是點擊來源。 請參 `hit_source` 閱「匯 [出使用指南」中的「資料欄參考](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) 」下方。 控制Cookie和其他方法用來識別訪客的順序。
* 查詢字串分隔字元(`?`)後面的所有項目，都是您要納入報表的資料。 如需 [影像請求中可包含之參數的完整清單](../validate/query-parameters.md) ，請參閱資料收集查詢參數。

## 常見問題解答

瞭解使用硬式編碼影像要求的常見問題。

**查詢字串參數是否區分大小寫？**

是。請確定查詢字串參數完全相符，否則不會記錄。 例如， `pagename` 不是有效的查詢字串參數，而 `pageName` 是。

**我可以在查詢字串中加入空格嗎？**

每個查詢字串參數的值都是URL編碼。 URL編碼會將URL中通常不合法的字元轉換為合法字元。 例如，空白字元可轉換為 `%20`. 請確定任何非英數字元的字元都是URL編碼。 當影像要求送達資料收集伺服器時，Adobe會自動將值進行URL解碼。

如需 [](https://www.w3schools.com/tags/ref_urlencode.asp) URL編碼如何運作的詳細資訊，請參閱W3Schools的HTML URL編碼參考。

**單一值最多可包含多少個字元？**

每個變數的最大長度不同。 大部分的流量變數可容納高達100個位元組，而大部分的轉換變數則容納高達255個位元組。 當影像要求送達資料收集伺服器時，Adobe會自動將這些值截斷至其最大長度。
