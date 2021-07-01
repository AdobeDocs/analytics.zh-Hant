---
title: 使用硬式編碼影像要求進行實施
description: 使用 HTML 影像標籤實施 Adobe Analytics (硬式編碼影像要求)
exl-id: 84247daf-c94b-456c-9824-6d4a0b3e6065
source-git-commit: de0424db27f9d1a3ce07632df8fd5e76b4d7bb4c
workflow-type: ht
source-wordcount: '672'
ht-degree: 100%

---

# 使用硬式編碼影像要求進行實施

Adobe 提供的 AppMeasurement 程式庫會編譯出現在頁面上的變數，然後以影像要求的形式傳送給 Adobe。您可以完全略過 AppMeasurement 程式庫，然後手動將影像要求傳送至 Adobe。此方法需要您手動制訂影像要求和查詢字串。

此實作方法可用於顯示外部來源影像的任何平台。它完全不依賴 JavaScript。

>[!NOTE]
>
> 雖然硬式編碼的影像要求易於設定，但在大型專案中卻難以除錯、維護和調整規模。繼續進行之前，請確定硬式編碼影像要求是您的最佳選項。

## 影像要求語法

以下是使用 HTML 的硬式編碼影像要求範例：

```html
<img src="https://example.data.adobedc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` 指定通訊協定。比對影像要求中使用的通訊協定與您網站其他部分使用的通訊協定。
* `example.data.adobedc.net` 是 [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) 變數中包含的值。
* `/b/ss/` 包含在所有影像要求中。它屬於 Adobe 資料收集伺服器上所儲存影像的檔案結構的一部分。
* `examplersid` 是您傳送資料的目的地報表套裝 ID。 如果有多個報表套裝，請用逗號且不含空格來區隔 ID (`examplersid1,examplersid2` 等)。
* `/1/` 是點擊來源。請參閱匯出使用手冊中[資料欄參考](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md)底下的 `hit_source`。控制用來識別訪客的 Cookie 和其他方法之順序。
* 查詢字串分隔字元 (`?`) 後面的所有項目，都是您要納入報表的資料。如需影像要求中可包含參數的完整清單，請參閱[資料彙集查詢參數](../validate/query-parameters.md)。

## Microsoft Outlook 中的硬式編碼影像要求

由於大部分電子郵件以 HTML 為基礎，因此可追蹤已開啟的電子郵件，並將該資料傳送至 Adobe Analytics。如果您的組織選擇使用此方法，請注意下列事項：

* 每次電子郵件轉譯都可增加一次計費伺服器呼叫。
* 僅追蹤支援 HTML 並允許影像的電子郵件用戶端。部分電子郵件用戶端 (如 Microsoft Outlook) 預設會封鎖外部影像。在收件者選擇下載外部影像之前，不會追蹤這些電子郵件。

若要撰寫包含影像要求的 Outlook 電子郵件，請執行下列操作：

1. 開啟 HTML 編輯器。如果沒有 HTML 編輯器，也可使用純文字檔案編輯器。
2. 在新的 HTML 檔案中，插入包在 `<body>` 標籤中的硬式編碼影像要求 `<img>` 標籤。
3. 儲存 HTML 檔案。
4. 開啟 Microsoft Outlook 並撰寫電子郵件。
5. 前往「插入」索引標籤，然後按一下&#x200B;**「附加檔案」**。選取您的影像要求 HTML 檔案。
6. 按一下「插入」旁的快顯選單，然後選取&#x200B;**「插入成文字」**。如果按一下沒有快顯選單的「插入」按鈕，HTML 檔案將變成無法使用的附件。

您的電子郵件似乎不會變更，因影像要求是 1x1 透明像素。如果您想查看影像要求以進行測試，請修改 HTML 檔案以加入邊框、其他文字或其他內容。

## 常見問答

瞭解使用硬式編碼影像要求的常見問題。

### 查詢字串參數是否區分大小寫？

是。請確定查詢字串參數完全一致，否則系統不會記錄。例如，`pagename` 不是有效的查詢字串參數，`pageName` 則有效。

### 可以在查詢字串中加入空格嗎？

每個查詢字串參數的值都會進行 URL 編碼。URL 編碼會將 URL 中通常不合規定的字元轉換為符合規定的字元。例如，空白字元可轉換為 `%20`。請確定所有非英數字元的都是以 URL 編碼。影像要求抵達資料收集伺服器時，Adobe 會自動對值進行 URL 解碼。

如需 URL 編碼運作方式的詳細資訊，請參閱 W3Schools 上的 [HTML URL 編碼參考](https://www.w3schools.com/tags/ref_urlencode.asp)。

### 單一值最多可包含幾個字元？

每個變數的長度上限均不同。大部分的流量變數可容納最多 100 個位元組，而轉換變數大多可容納最多 255 個位元組。影像要求抵達資料收集伺服器時，Adobe 會自動將這些值截斷至其長度上限。
