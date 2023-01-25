---
title: 作業系統
description: 訪客的作業系統。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 17c441f8855b8ca0604076763817de8d4d3b8efb
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 34%

---

# 作業系統

「作業系統」維度會顯示訪客使用的作業系統和版本。如果您的 Web 屬性中有作業系統專屬的功能，此維度可協助您了解哪些作業系統最常見。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。

## 維度項目

維度項目包括訪客使用的作業系統。範例包括 `"Windows 10"`、`"OS X 10.15"`、 和 `"Android 9"`。

## 標籤和定義的變更

以下是使用者代理和Adobe Analytics報表中如何呈現作業系統的特定問題清單。

### 變更Apple作業系統的命名慣例：

從11版開始，我們將使用MacOS（而非OS X）來指稱Apple作業系統。

範例：

* &quot;OS X 10.15&quot;(請參閱下方關於10.15.7版的附註，而非UA字串中的表示)。
* &quot;MacOS 11.0.0

### Mac OS版本在10.15.7版之後的使用者代理中不正確 

Apple電腦上的使用者代理會將作業系統版本顯示為10.15.7，即使是較新版本亦然。 這樣做是因為將第11版納入UA顯然造成了一些網站的問題。 對於 *所有瀏覽器* 與Google在Chromium瀏覽器上「凍結」使用者代理無關。

請注意，用戶端提示在平台版本提示(「Sec-CH-UA-Platform-Version」)中包含正確的版本。 這是高熵提示，因此Adobe不會自動收集。 請參閱 [Adobe Analytics提示常見問題集](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 詳細了解如何收集高熵提示。

### 從Windows 11開始，用戶代理中的Windows版本不正確

自2023年1月起，所有瀏覽器中的使用者代理將Windows 11顯示為Windows 10。

請注意，用戶端提示在平台版本提示(「Sec-CH-UA-Platform-Version」)中包含正確的版本。 這是高熵提示，因此Adobe不會自動收集。 請參閱 [Adobe Analytics提示常見問題集](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 詳細了解如何收集高熵提示。
