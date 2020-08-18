---
title: 使用硬式編碼影像要求進行實施
description: 使用 HTML 影像標籤實施 Adobe Analytics (硬式編碼影像要求)
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 66%

---


# 使用硬式編碼影像要求進行實施

Adobe 提供的 AppMeasurement 程式庫會編譯出現在頁面上的變數，然後以影像要求的形式傳送給 Adobe。您可以完全略過 AppMeasurement 程式庫，然後手動將影像要求傳送至 Adobe。此方法需要您手動制訂影像要求和查詢字串。

此實施方法可用於顯示外部來源影像的任何平台。它完全不依賴 JavaScript。

>[!NOTE]
>
> 雖然硬式編碼的影像要求易於設定，但在大型專案中卻難以除錯、維護和調整規模。繼續進行之前，請確定硬式編碼影像要求是您的最佳選項。

## 影像要求語法

以下是使用 HTML 的硬式編碼影像要求範例：

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` 指定通訊協定。比對影像要求中使用的通訊協定與您網站其他部分使用的通訊協定。
* `example.sc.omtrdc.net` 是 [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) 變數中包含的值。
* `/b/ss/` 包含在所有影像要求中。它屬於 Adobe 資料收集伺服器上所儲存影像的檔案結構的一部分。
* `examplersid` 是您傳送資料的目的地報表套裝 ID。
* `/1/` 是點擊來源。請參閱匯出使用手冊中[資料欄參考](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)底下的 `hit_source`。控制用來識別訪客的 Cookie 和其他方法之順序。
* 查詢字串分隔字元 (`?`) 後面的所有項目，都是您要納入報表的資料。如需影像要求中可包含參數的完整清單，請參閱[資料彙集查詢參數](../validate/query-parameters.md)。

## Microsoft Outlook中的硬式編碼影像要求

由於大部分電子郵件都是以HTML為基礎，因此可追蹤已開啟的電子郵件，並將該資料傳送至Adobe Analytics。 如果您的組織選擇使用此方法，請注意下列事項：

* 每個電子郵件轉譯都可增加計費伺服器呼叫。
* 僅追蹤支援HTML並允許影像的電子郵件用戶端。 有些電子郵件用戶端（例如Microsoft Outlook）預設會封鎖外部影像。 在收件者選擇下載外部影像之前，不會追蹤這些電子郵件。

要構成包含映像請求的Outlook電子郵件，請執行以下操作：

1. 開啟HTML編輯器。 如果HTML編輯器不可用，則純文字檔案編輯器也可以工作。
2. 在新的HTML檔案中，插入硬式編碼影像要求標 `<img>` 簽，並包裝在標 `<body>` 簽中。
3. 儲存HTML檔案。
4. 開啟Microsoft Outlook並撰寫電子郵件。
5. 轉到「插入」頁籤，然後按一下「附 **加檔案」**。 選取您的影像要求HTML檔案。
6. 按一下「插入」旁的快顯功能表，然後選取「 **插入為文字」**。 如果按一下沒有彈出菜單的「插入」按鈕，HTML檔案將變成一個無效的附件。

您的電子郵件似乎不會變更，因為影像要求是1x1透明像素。 如果您想查看影像要求以進行測試，請修改HTML檔案以包含邊框、其他文字或其他內容。

## 常見問題集

瞭解使用硬式編碼影像要求的常見問題。

### 查詢字串參數是否區分大小寫？

是。請確定查詢字串參數完全一致，否則系統不會記錄。例如，`pagename` 不是有效的查詢字串參數，`pageName` 則有效。

### 可以在查詢字串中加入空格嗎？

每個查詢字串參數的值都會進行 URL 編碼。URL 編碼會將 URL 中通常不合規定的字元轉換為符合規定的字元。例如，空白字元可轉換為 `%20`。請確定所有非英數字元的都是以 URL 編碼。影像要求抵達資料收集伺服器時，Adobe 會自動對值進行 URL 解碼。

如需 URL 編碼運作方式的詳細資訊，請參閱 W3Schools 上的 [HTML URL 編碼參考](https://www.w3schools.com/tags/ref_urlencode.asp)。

### 單一值最多可包含幾個字元？

每個變數的長度上限均不同。大部分的流量變數可容納最多 100 個位元組，而轉換變數大多可容納最多 255 個位元組。影像要求抵達資料收集伺服器時，Adobe 會自動將這些值截斷至其長度上限。
